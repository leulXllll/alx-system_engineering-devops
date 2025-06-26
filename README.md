# alx-system_engineering-devops
## Simple web stack

-Lets say a client wants to access our server with domain name www.foobar.com 
1. The client asks DNS server for the ip address of www.foobar.com , the dns responds with 8.8.8.8 ip address then the client requests for web page resources 
2. The network will pass through firewall then reaches the webserver 
3. he web server will respond to appropriate web resources

-A server is physical computer or VM machine that helps us host our web server , applicaion server , daabase server and so on 
-A domain name prevens us to memorize the ip address of servers by allowing us to use natural language
- www.foobar.com is a subdomain name while foobar.com is the root domain name
-The web server is a software that responds to HTTP requests with static content like HTML, Css and Javascript
- The application server responds to business logic or dnamic conen
- he daabase helps us sore information in a logical way that makes it easier for CRUD operaions
- The server is using HTTP protocol o communicaet with the client
- In this infrastructure there are some issues like
 1. SPOF(single point of failure): which means if one part or single par of the system malfunctions it could bring down the whole system for instance if the web server failed, users could not access the server.
 2.High Downtime : meaning if we want to push our updates we need to shutdown our server push our code and turn it back again this causes high revenue loss,and its difficult to test.
 3.Less scalable: if there is high level of incoming traffic we can't scale or grow the system based on needed traffic 

## Distributed web infrastructure
- In this improvements I have added additional 2 web servers by scalling it horizontally , I have also added Load balancer to distribute the networks and single database 
-The load balancer should be configured with round robin algorithm which works by sequentially aligning the requests for each web server after the third one it will direct traffic to the first server 

-Active-Active: means each web servers are responding o requests
-Active-Passive: means here are web servers sitting there idle and if the active servers fail this servers will detect the failure and be activated .

-The Load balancer enables an Active-Active which means each server respondes to requests and there is no idle web-server waiting .

-Primary-Replica (or Master-Slave) database cluster is a common architecture for data
replication. It involves a single database instance designated as the "Primary" (or "Master") and one or more database instances designated as "Replicas" (or "Slaves")

- Issues
1. Security: There are no firewalls protecting the websservers 
- they are using HTTP protocol which means it is not encrypted leads to man in the middle attack 
2. No monitoring tools: there are no monitoring tools which means we can't measure our performance , if our web server is properly working
3. SPOF: In case of cyber attack the whole system will fail because lack of security 