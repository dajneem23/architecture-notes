# Master-slave is not a new word in the world of databases. In fact, it has been in usage for quite some time now. It revolves around producing seamless database connectivity between enterprises and their users.
The master-slave design has been instrumental in alleviating system failures and performance issues. It has helped in the optimization of multiple databases.
In this post, we will understand everything about this simple but widely useful concept.
### Table of Contents
- [Master-slave is not a new word in the world of databases. In fact, it has been in usage for quite some time now. It revolves around producing seamless database connectivity between enterprises and their users.](#master-slave-is-not-a-new-word-in-the-world-of-databases-in-fact-it-has-been-in-usage-for-quite-some-time-now-it-revolves-around-producing-seamless-database-connectivity-between-enterprises-and-their-users)
    - [Table of Contents](#table-of-contents)
  - [WHAT IS THE MASTER-SLAVE DATABASE?](#what-is-the-master-slave-database)
  - [STEPS TO ACHIEVE MASTER-SLAVE REPLICATION](#steps-to-achieve-master-slave-replication)
  - [PROS OF MASTER-SLAVE DATABASE ARCHITECTURE](#pros-of-master-slave-database-architecture)
  - [CONS OF MASTER-SLAVE ARCHITECTURE](#cons-of-master-slave-architecture)
  - [VERDICT](#verdict)
  - [References](#references)
## WHAT IS THE MASTER-SLAVE DATABASE?
As the name suggests, the master-slave is a database architecture divided into a master database and slave databases. The slave database serves as the backup for the master database.
The master database is actually the keeper of the data resources and also the place where all the writing requests are performed. The reading operations are spread across multiple slave databases relative to the master database. This architecture is used to enhance the site's reliability to a greater extent.
Imagine a situation where your site is bombarded with multiple data requests causing a surge in web traffic. Now if there is only one master database, then it will be overloaded, making the site slower for all your users.
To scale out your application, you need two data sources- one to handle the write operations and the other one to handle the read operations. And that’s where master-slave architecture comes in handy.
Basically, master-slave databases involve caching data from the master database to the slave databases. This replication process helps database administrators to replicate copies of the parent database to multiple servers simultaneously. Whenever updates are pushed to the master database, they are made to ripple through the slave databases in contact.
Now if you are still skeptical about the benefit of the master-slave database, here is another scenario.
Imagine you are maintaining a large-scale application and your server goes down. After a few debugging sessions, you find out that it is due to the read/write requests to your database server. In such cases, opting for a master-slave database architecture is recommended. Distributing load across slave nodes, this architecture can help your application scale-out accomodating your growing users.
## STEPS TO ACHIEVE MASTER-SLAVE REPLICATION
- To set up the master database, you can use a MySQL server.
- Now create a new user for your slave database.
- Next, select the position to map the data and then create a MySQL dump file to move the data resources.
- After creating a MySQL dump file, the next step is to configure your slave servers. Open the configuration file of the slave server and bind the IP address of your master to your slave servers and restart your slave servers.
Now that you have created a data dump file in the previous steps, its time to import them to the slave databases. Make sure you have included all the data dump files including the updated IP address of the master server, log files, password, and other RBA(Role-Based Access) credentials to the slave databases.
- Start the slave server and check if your replication is successful.
- Test the data replication you have just set up. Create a database in your master server and check if it is reflected in your slave databases. For example, create a database named ‘testdb’ in your master database. Now login into your slave server and list out the databases. If you see the ‘testdb’ database in your slave server, then your master-slave database replication is working fine.
## PROS OF MASTER-SLAVE DATABASE ARCHITECTURE
- Produce backups - Obviously, the major utility of master-slave database architecture is its ability to provide reliable backups through their chain of slave databases. The slave database can be shut down without affecting the operations of the master database. This is because the snapshots of the live data will be replicated onto the slave database and the data resources will be intact even after a failure in the master database.
- Scale out the application - When users multiply and your application’s usage surges rapidly, it is important to scale out your application to provide a seamless user experience to your audience. The master-slave database architecture can be used for scaling out your application by distributing your data load across multiple databases.
- Split your work without causing a mess- You can use your slave nodes to gauge the required data and make a detailed report on it and use the master node to push new updates and features onto your application server.
- Top-notch performance - It is extremely fast and fetches data without any issues, imposing no restrictions regarding performance and time to load the data.
## CONS OF MASTER-SLAVE ARCHITECTURE
- Asynchronous replication fails at times - Asynchronous means two or more operations taking place in a system that is independent and does not rely upon or affect each other. This asynchronous replication followed in the master-slave database is not very reliable as the changes committed to the master may not be reflected in the slave nodes if there is a failure in the master node.
- Write operations to master are hard to scale - Write requests to master can hardly be scaled. One of the only few options to scale the writing requests is to increase the compute capacity(CPU and ROM) of the master database.
- No automatic failover - In case a master fails, a slave should be pushed to take the place of the master. No automatic failover replacement ensues.
- Binary log has to be read each time data is copied - Each slave adds load to the master as the binary log has to be read before copying data to the slave nodes.
## VERDICT
There are several database replication techniques such as master-master database, multi master database, each having its own pros and cons. As the need for the cloud has peaked in this pandemic, companies switching their data resources online, have heavily started relying upon master-slave architecture.
Although it is extremely robust, the underlying complexity is difficult and the cost for renting and maintaining separate databases and servers may outweigh the benefits offered by this master-slave architecture. You may need a dedicated team of experts to pull off this architecture on a large-scale application infrastructure

------------
## References
- [master-slave-database-concepts-for-beginner](https://www.partech.nl/nl/publicaties/2021/12/master-slave-database-concepts-for-beginners#)
- [Master/slave (technology)](https://en.wikipedia.org/wiki/Master/slave_(technology))