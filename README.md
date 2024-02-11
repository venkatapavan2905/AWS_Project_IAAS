In this Project, entire on-prem infra is shifted to AWS Cloud following Lift and Shift Approach. Since every service is created on EC2 instances this comes under Infrastructure as a service.



![image](https://github.com/venkatapavan2905/AWS_Project_IAAS/assets/138016465/361e6007-468c-4faa-9c12-cfb18f707d59)

                                           AWS IAAS Architecture


1. SSL certificate is generated from AWS Certificate Manager (ACM) and verified in Godaddy to enable https connection.
2. Tomcat9 is launched in Ubuntu and Mysql, RabbitMQ, Memcached services are launched on almalinux9 and provisioned through userdata scripts.
3. Connection from Tomcat services to the backend services is provisioned through routes(privated hosted zone) in Route53 and security group of app project.
4. DNS names of backed services are updated in application.properties of /src/main/java/resources/application.properties.
5. Application is Compiled and build using Maven on Visual Studio code and artifact is uploaded using awscli to S3 bucket.
6. Artifact is copied to tomacat instance from S3 bucket and restarted the service.
7. Image is created with the working appliaction and used to create a template for auto scaling group.
8. Load balancer and Auto scaling groups are configured to provision High Availability and Fault tolerance.




![image](https://github.com/venkatapavan2905/AWS_Project_IAAS/assets/138016465/28a35055-d92b-452d-bf2e-efecb3aa5845)

