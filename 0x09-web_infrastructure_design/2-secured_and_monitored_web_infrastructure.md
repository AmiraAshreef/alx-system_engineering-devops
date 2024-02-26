Whiteboard Design:

User's Device: Represents the user's computer or smartphone.
Internet: A cloud connecting all devices.
Firewall 1: Filters incoming traffic at the network perimeter.
Load Balancer (HAproxy): Distributes traffic across web servers.
SSL Termination: Decrypts HTTPS traffic at the load balancer.
Firewall 2: Filters traffic between the load balancer and web servers.
Web Server 1 (Nginx): Runs on Server 2, serves static content.
Web Server 2 (Nginx): Runs on Server 3, serves static content.
Firewall 3: Filters traffic between web servers and the application server.
Application Server: Runs on Server 1, handles application logic and database interaction.
Database Cluster (MySQL):
Primary Node: Stores and manages the main copy of the data.
Replica Node: Synchronizes data from the primary for read operations and failover.
Monitoring Clients: Installed on each server, collecting data for Sumologic or other monitoring services.
Arrows: Connect components to show data flow.
Explanation:

Additional Elements:

Firewalls: Provide three layers of security:
Firewall 1: Blocks malicious traffic at the network edge.
Firewall 2: Filters traffic between the load balancer and web servers, restricting unauthorized access.
Firewall 3: Protects the application server from unauthorized access.
SSL Termination: Decrypts HTTPS traffic at the load balancer, improving performance and simplifying certificate management.
Monitoring Clients: Collect performance and health data from servers, applications, and databases, enabling proactive monitoring and troubleshooting.
Specifics:

Firewalls: Act as security gateways, inspecting incoming and outgoing traffic based on predefined rules. They block suspicious traffic and protect against cyberattacks.
HTTPS: Encrypts communication between the user's browser and the web server, ensuring data privacy and integrity.
Monitoring: Tracks server performance, application health, and database activity. It helps identify potential issues before they impact users and enables performance optimization.
Monitoring Tool Data Collection: Monitoring clients collect data through various methods, including:
Agent-based: Software installed on servers collects data from system resources, applications, and databases.
API integration: Monitoring tools interact with server APIs to retrieve performance metrics.
Log file monitoring: Parsing server logs for relevant information.
Monitoring Web Server QPS: You can monitor web server QPS (queries per second) using metrics like:
HTTP request rate: Number of HTTP requests received by the server per second.
Database query rate: Number of database queries executed per second.
Response time: Average time taken to respond to requests.
Potential Issues:

SSL Termination at Load Balancer: While convenient, it can introduce a single point of failure (SPOF) if the load balancer fails. Consider terminating SSL at individual web servers for better redundancy.
Single MySQL Write Server: The primary node is a SPOF. Implement a multi-master or geographic replication strategy for high availability and disaster recovery.
Identical Server Components: If all servers have the same configuration, a single vulnerability can affect all of them. Consider separation of concerns by dedicating servers to specific roles (web server, application server, database).
