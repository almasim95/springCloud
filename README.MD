This is a simple project that demonstrates the communication between spring-cloud server 
with local configuration and spring-cloud client. 

Step 1) Start spring cloud server application

Step 2) Start spring client application with one of the follwing VM arguments:

1) -Dspring.profiles.active=dev -Dserver.port=8080
2) -Dspring.profiles.active=prod -Dserver.port=8090

Step 3) Open brower at http://localhost:8080 or  http://localhost:8090 based on previous choice

Step 4)Edit coresponding .yml file based on choice at Step 2) from:

 spring-boot-config-server\src\main\resources\config\simple-service:

 -> simple-service-dev.yml
 or
 ->simple-service-prod.yml

Step 5) Run from CMD: 
"curl -H "Content-Type: application/json" -d {} http://localhost:8080/actuator/refresh"
or
"curl -H "Content-Type: application/json" -d {} http://localhost:8090/actuator/refresh"
based on choice from Step 2)

Step 5) Refresh page from Step 2) in browser.
Message should now be updated.