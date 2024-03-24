![web_infrastructure_task 0](https://github.com/Lamba237/alx-system_engineering-devops/assets/129569062/e1025bc1-2c84-4bf6-b8a4-c83163dfbb61)


explain some specifics about this infrastructure:
1) For every additional element, why you are adding it:
The reason why I am adding every other element is so that the infrastructure can avoid Single point of Failure and also become
have the ability to recieve more traffic
2) What distribution algorithm your load balancer is configured with and how it works
We make use of the round robin algorithm for distribution, here Requests are served by the server sequentially one after another. After sending the request to the last server, it starts from the first server again.
3) Is your load-balancer enabling an Active-Active or Active-Passive setup, explain the difference between both

My load balancer is enabling an Active-Active.
-> An Active-Active solutions deploy two or more active system instances and can be used to improve scalability as well as provide high availability.
->Active-passive solutions deploy an active instance that handles requests and a passive instance that is on standby

4) How a database Primary-Replica (Master-Slave) cluster works
   A Primary-Replica setup configures one server to act as the Primary server and the other server to act as a Replica of the Primary server. However, the Primary server is capable of performing read/write requests whilst the Replica server is only capable of performing read requests.

5) The difference between the Primary node and the Replica node in regard to the application.
The Primary node is responsible for all the write operations the site needs whilst the Replica node is capable of processing read operations, which decreases the read traffic to the Primary node.

Issues With This Infrastructure
There are multiple SPOF (Single Point Of Failure).
For example, if the Primary MySQL database server is down, the entire site would be unable to make changes to the site 
Security issues.
The data transmitted over the network isn't encrypted using an SSL certificate so hackers can spy on the network. There is no way of blocking unauthorized IPs since there's no firewall installed on any server.
No monitoring.
We have no way of knowing the status of each server since they're not being monitored.
