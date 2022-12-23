# Lab 6 report

## Tasks

 - Launch service registration server on port 1111 (Eureka Server).
 - Launch `accounts` and `web` services on ports 2222 and 3333 respectively.
 - Launch another `accounts` service on port 4444 and check registration on Eureka server.
 - Kill `accounts` service on port 2222. What happens when try to make a request to the `web`? Why?

## Eureka server

First of all we need to launch the service registration server on port 1111.
![eurekaConsole](img/eurekaConsole.png)

Once it's running, let's check it on the web browser
![eurekaCapture1](img/eurekaCapture1.png)

## Accounts service

Now that the Eureka server is up, we can launch the `accounts` service
![account2222Console](img/accounts2222Console.png)

Let's check now if it's in the registration server
![accounts2222Registration](img/accounts2222Registration.png)

Everything seems to work fine.
## Web service

And finally we may launch the `web` service.
![web3333Console](img/web3333Console.png)
![web3333Registration](img/web3333Registration.png)

## Launching additional service

We want to try now what happens when you launch another `accounts` service on port 4444.
![account4444Console](img/account4444Console.png)
![accountsDoubleService](img/accountsDoubleService.png)

We can see both services are registered on ports 2222 and 4444 respectively.

## Killing one of the services

We want to know if the web is going to work even if we kill the first `accounts` service (port 2222). 
In order to do that, we kill the service process `Ctrl`+`C`. And do a request to the web.
![accounts4444Registration](img/accounts4444Registration.png)
![webResponse](img/webResponse.png)

### Why?

If at least one `accounts` service is running, it doesn't matter on which port it's being launched as long as it's registered.
Eureka server will tell `web` service where to find it.


