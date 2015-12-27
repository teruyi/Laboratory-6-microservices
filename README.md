# Web Engineering 2015-2016 / Microservices
##1.- The two microservices are running and registered (two terminals, logs screenshots).
### Account Microservice
![Account Microservice running and registered](https://raw.github.com/teruyi/Laboratory-6-microservices/master/account.png)
### WebService Microservice
![Web Microservice running and registered](https://raw.github.com/teruyi/Laboratory-6-microservices/master/web.png)

##2.- The service registration service has the two microservices registered (a third terminal, dashboard screenshots)
![Dashboard showing registered services](https://raw.github.com/teruyi/Laboratory-6-microservices/master/dashboard.png)

##3.- A second account microservice is running in the port 4444 and it is registered (a fourth terminal, log screenshots).
![Account Microservice running on port 4444](https://raw.github.com/teruyi/Laboratory-6-microservices/master/account-4444.png)

##4.- A brief report describing what happens when you kill the microservice with port 2222. Can the web service provide information about the accounts? Why?
At firts when you kill the account microservice in port 2222, if you try to do an operation with the web microservice, first shows "Refused connection" errores. A few seconds after this, it shows "No instances available for ACCOUNTS-SERVICE". At last, thirty seconds after this (more-less), it discover in port 4444 the new account microservices and starts working again.

What happens when the account server with port 2222 is killed:

The Web microservice tries to communicate with it but its fails. Now the web microservices needs some time to realize that it is down, then the web microservices asks the registration services for another account microservices. The registration microservices tell the new port for the account microservices (4444), Finally it starts working again.