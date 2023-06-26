# architecture-notes

## 1. Load Balancers
- [ ] [HAProxy](https://www.haproxy.com/)
- [ ] [Nginx](https://www.nginx.com/)
#### 1. round + robin 
- [ ] Round Robin Load Balancing is a simple way to distribute client requests across a group of servers. The algorithm instructs the load balancer to forward a client request to each server in turn, going down the list of servers in the group. Once the last server in the list has been reached, the algorithm instructs the load balancer to go back to the top of the list and repeat the process again 1. Weighted Round Robin Load Balancing is similar to Round Robin Load Balancing, but it allows you to set values unequally. Whereas Round Robin requires an equal distribution, Weighted Load Balancing methods allow you to set values unequally 23.
#### 2. least + connections
- [ ] Least Connections Load Balancing is a dynamic load balancing algorithm where client requests are distributed to the application server with the least number of active connections when the client request is received. This method minimizes the chances of server overload, as it only sends requests to servers with fewer active connections
#### 3. ip + hash
- [ ] IP Hash Load Balancing is a load balancing algorithm that uses the client’s source and destination IP addresses to generate a unique hash key to tie the client to a particular server. This method ensures that requests from the same client will always be directed to the same server except when this server is unavailable 1
#### 4. least + time
-  [ ] Least Time Load Balancing is a load balancing algorithm that distributes requests to the server selected by a formula that combines the fastest response time and fewest active connections. This method ensures that requests are directed to the server with the shortest average response time and the fewest active connections 
#### 5. weighted + round + robin
- [ ] Weighted Round Robin Load Balancing is similar to Round Robin Load Balancing, but it allows you to set values unequally. Whereas Round Robin requires an equal distribution, Weighted Load Balancing methods allow you to set values unequally 23.