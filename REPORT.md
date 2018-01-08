# Web Engineering 2017-2018 / Microservices

## Brief report

* The two microservices are running and registered

![AccountServiceRunning_AccountServiceLog](images/0_accountServerRunningAndRegistered_LogAccountServer.png)
<center>Image 1. Account service is running and registered</center>

![AccountServiceRunning_RegistrationServerLog](images/1_accountServerRegistered_LogRegistrationServer.png)
<center>Image 2. Account service is registered in Registration Server</center>

![WebServiceRunning_WebServiceLog](images/2_webServerRunningAndRegistered_LogWebServer.png)
<center>Image 3. Web service is running and registered</center>

![WebServiceRunning_RegistrationServerLog](images/3_webServerRegistered_LogRegistrationServer.png)
<center>Image 4. Web service is registered in Registration Server</center>
<br>

* The service registration service has the two microservices registered

![RegistrationServerDashboard](images/4_webServiceRegisteredInEureka.png)
<center>Image 5. Registration Server Dashboard</center>
<br>

* A second account microservice is running in the port 4444 and it is registered

![AnotherAccountServiceRunning_AccountServiceLog](images/5_anotherAccountServiceRegisteredInEureka_LogAccountServer.png)
<center>Image 6. Another Account service is running and registered</center>

![AnotherAccountServiceRunning_RegistrationServerLog](images/6_anotherAccountServiceRegisteredInEureka_LogRegistrationServer.png)
<center>Image 7. Another Account service is registered in Registration Server</center>

![RegistrationServerDashboardWithAnotherAccountService](images/7_anotherAccountServiceRegisteredInEureka.png)
<center>Image 8. Registration Server Dashboard with another Account Service added</center>
<br>

* A brief report describing what happens when you kill the microservice with port 2222. Can the web service provide information about the accounts? Why?

The web service knows that there are two account microservices, since they are duplicated.
This cause that the web service will be able to communicate with both of them, 
depending on which one the Eureka registration services provide.

If we kill the account service in the port 2222, the web service will continue using 
this service **until Eureka update its list of available services**, and therefore realizes
that the service is offline.