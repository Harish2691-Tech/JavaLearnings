API Gateway and Load balance ?
These both sit between users and backend.

API Gateway : 
  1. API gateway act as a single entry point and decides which backend service should handle the request.
  2. Also take care of 
       1. Authentication
       2. Rate limitting
       3. Throttling
       4. Logging
       5. Request Transformation

Suppose our one service(Product service) has multiple server instances, this is where Load balancer comes in.

Load balancer :
  It distributes incoming product request across the available servers helping improve availability and scalabity. 


Remember :
API gateway -> Which service handle this request. API routing and policies.
Load balancer -> Which instance of the service handle this request. It focus on traffic distribution.

------






         
     
  

   
