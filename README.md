# CircuitBreaker Testing

</br></br>
<p><b>PoC To Perform Microservices CircuitBreaker Testing.</b></br>
<p>There are 2 MS here: a.PassengerDetails b.Airlines</br>
<p>If we design our systems on microservice based architecture, we will generally develop many Microservices and those will interact with each other heavily in achieving certain business goals. Now, all of us can assume that this will give expected result if all the services are up and running and response time of each service is satisfactory.

Now what will happen if any service, of the current Eco system, has some issue and stopped servicing the requests. It will result in timeouts/exception and the whole Eco system will get unstable due to this single point of failure.

Here circuit breaker pattern comes handy and it redirects traffic to a fall back path once it sees any such scenario. Also it monitors the defective service closely and restore the traffic once the service came back to normalcy.

So circuit breaker is a kind of a wrapper of the method which is doing the service call and it monitors the service health and once it gets some issue, the circuit breaker trips and all further calls goto the circuit breaker fall back and finally restores automatically once the service came back !! 

</br></br>

<p>mvn clean install<br>
java -jar target\spring-hystrix-student-service-0.0.1-SNAPSHOT.jar

mvn clean install<br>
java -jar target\spring-hystrix-school-service-0.0.1-SNAPSHOT.jar  


http://localhost:8098/getPassengerDetailsForAirlines/Indigo 
http://localhost:8098/getPassengerDetailsForAirlines/Indigo

http://localhost:9098/hystrix
http://localhost:9098/hystrix.stream 
