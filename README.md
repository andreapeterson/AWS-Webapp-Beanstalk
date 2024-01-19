# AWS-Webapp-Beanstalk
Utilizing AWS Elastic Beanstalk to host web app. Building on my last AWS multi-tier architecture [here](https://github.com/andreapeterson/AWS-MultiTier-Architecture), I restructured it to incorporate mostly PaaS and SaaS services.

![IMG_B1263C6C9047-1](https://github.com/andreapeterson/AWS-Webapp-Beanstalk/assets/134665743/dd7e4e3d-c3ae-410a-942e-146d87e3fd28)

For the frontend, I used AWS Elastic Beanstalk for the Tomcat server. Beanstalk also manages a load balancer, auto-scaling, and an S3 bucket for storing the artifacts as well.

For the backend: I used RDS for the database, ElastiCache for caching, and ActiveMQ for RabbitMQ - so I am no longer managing my own servers directly myself on EC2. Additionally, I stuck with DNS+ACM to deliver HTTPS through my own domain name.

For details on some specifics of the project, I created a temporary EC2 instance to initialize the database by running SQL queries. I still used Maven to build an artifact but this time I uploaded it directly to the Beanstalk environment via console.

I am doing a course from the wonderful Imran Teli, so the code above comes mostly from [here](https://github.com/hkhcoder/vprofile-project). I edited the 'applications.properties' file so my Tomcat instances can have the endpoints for my backend services as well as customized the 'welcome.jsp' and images folder to add content specific for my pup, Milo.
![image](https://github.com/andreapeterson/AWS-Webapp-Beanstalk/assets/134665743/50f4476e-7e7d-4f4e-beda-0ade0ffb857e)

