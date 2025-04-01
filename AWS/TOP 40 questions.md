## **AWS Cloud Practitioner Certification Exam MCQs**

**So, let's dive into the questions and expand your understanding of AWS cloud computing:*
  

==13. Which AWS service can be used to host a static website?==

==a) Amazon S3==

==b) Amazon EC2==

==c) AWS Lambda==

==d) Amazon RDS==

- ==Correct answer:==
    -  ==a) Amazon S3  
        Explanation: Amazon S3 can be used to host a static website by storing the website's HTML, CSS, JavaScript, and other files. You can configure S3 to serve the static website content directly to users, making it a simple and cost-effective solution for hosting static websites.==
  

==**22. Which AWS service provides a fully managed, scalable, and serverless data integration service?**==

==a) Amazon S3==

==b) AWS Glue==

==c) AWS Data Pipeline==

==d) Amazon RDS==

==**Correct answer:**== ==b) AWS Glue==

==**Explanation:**== ==AWS Glue is a fully managed, serverless data integration service that makes it easy to prepare and load data for analytics. It automatically generates code to extract, transform, and load (ETL) data from various sources and catalogs the metadata for easy discovery.==

  

  

==**23. What is the primary purpose of AWS Elastic Beanstalk?**==

==a) Scaling EC2 instances automatically==

==b) Managing containerized applications==

==c) Deploying serverless functions==

==d) Simplifying the deployment of web applications==

==**Correct answer:**== ==d) Simplifying the deployment of web applications==

==**Explanation**====: AWS Elastic Beanstalk is a platform as a service (PaaS) offering that makes it easy to deploy, run, and scale web applications. It abstracts the underlying infrastructure details and allows developers to focus on writing code while AWS handles the deployment and management aspects.==


==**30. Which AWS service provides managed file storage for EC2 instances?**==

==a) Amazon S3==

==b) AWS Lambda==

==c) Amazon EFS==

==d) Amazon RDS==

==**Correct answer:**== ==c) Amazon EFS==

==**Explanation:**== ==Amazon Elastic File System (EFS) is a fully managed file storage service that provides scalable and highly available file storage for use with Amazon EC2 instances. It supports multiple EC2 instances accessing the same file system concurrently.==


  

==**33. Which AWS service can be used to process and analyze large datasets in a distributed computing environment?**==

==a) Amazon S3==

==b) AWS Lambda==

==c) Amazon Redshift==

==d) Amazon EMR==

==**Correct answer:**== ==d) Amazon EMR==

==**Explanation:**== ==Amazon Elastic MapReduce (EMR) is a fully managed big data processing service that enables processing and analyzing large datasets using popular frameworks such as Apache Hadoop, Apache Spark, and Presto. It simplifies the setup, configuration, and management of distributed computing clusters.==

  

  

==**34. What AWS service can be used to host and manage databases in the cloud?**==

==a) Amazon S3==

==b) AWS Lambda==

==c) Amazon RDS==

==d) AWS Glue==

==**Correct answer:**== ==c) Amazon RDS==

==**Explanation:**== ==Amazon Relational Database Service (RDS) is a fully managed service that provides resizable and scalable relational databases in the cloud. It supports popular database engines like MySQL, PostgreSQL, Oracle, and SQL Server.==

  

  

# ==**35. Which AWS service can be used to distribute traffic across multiple EC2 instances or load balancers?*==

==a) Amazon Route 53==

==b) AWS Elastic Beanstalk==

==c) AWS Auto Scaling==

==d) Amazon CloudFront==

==*Correct answer:* a) Amazon Route 53==

==*Explanation:* Amazon Route 53 is a scalable domain name system (DNS) web service that can be used for routing users to different resources in a highly available and cost-effective manner. It can route traffic to multiple EC2 instances or load balancers to achieve load balancing and fault tolerance.==


1. ==Which services can be used to deploy applications on AWS? (Choose two.)==
    
    - ==A. AWS Elastic Beanstalk==
    - ==B. AWS Config==
    - ==C. AWS OpsWorks==
    - ==D. AWS Application Discovery Service==
    - ==E. Amazon Kinesis==


    ==Correct Answer: AC==
    
    
2. ==Which AWS service can be used to provide an on-demand, cloud-based contact center?==
    
    - ==A. AWS Direct Connect==
    - ==B. Amazon Connect==
    - ==C. AWS Support Center==
    - ==D. AWS Managed Services==
    
    ==Correct Answer: B==
    
3. ==What tool enables customers without an AWS account to estimate costs for almost all AWS services?==
    
    - ==A. Cost Explorer==
    - ==B. TCO Calculator==
    - ==C. AWS Budgets==
    - ==D. AWS Pricing Calculator==
    
    
    ==Correct Answer: D==
    
    
5. Which pricing model would result in maximum Amazon Elastic Compute Cloud (Amazon EC2) savings for a database server that must be online for one year?
    
    - A. Spot Instance
    - B. On-Demand Instance
    - C. Partial Upfront Reserved Instance
    - D. No Upfront Reserved Instance
     
     
     
     answer is c 
    
6. ==A company has a MySQL database running on a single Amazon EC2 instance. The company now requires higher availability in the event of an outage. <br/> Which set of tasks would meet this requirement?==
    
    - ==A. Add an Application Load Balancer in front of the EC2 instance==
    - ==B. Configure EC2 Auto Recovery to move the instance to another Availability Zone==
    - ==C. Migrate to Amazon RDS and enable Multi-AZ==
    - ==D. Enable termination protection for the EC2 instance to avoid outages==
    
    <details markdown=1><summary markdown="span">Answer</summary>
    
    Correct Answer: C
    
    Explanation: [https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Concepts.MultiAZ.html](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Concepts.MultiAZ.html)
    
    </details>
    
7. A company wants to ensure that AWS Management Console users are meeting password complexity requirements. <br/> How can the company configure password complexity?
    
    - A. Using an AWS IAM user policy
    - B. Using an AWS Organizations service control policy (SCP)
    - C. Using an AWS IAM account password policy
    - D. Using an AWS Security Hub managed insight
    
    <details markdown=1><summary markdown="span">Answer</summary>
    
    Correct Answer: C
    
    Explanation: [https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_passwords_account-policy.html](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_passwords_account-policy.html)
    
    </details>
    
8. Under the AWS shared responsibility model, which of the following is the customer's responsibility?
    
    - A. Patching guest OS and applications
    - B. Patching and fixing flaws in the infrastructure
    - C. Physical and environmental controls
    - D. Configuration of AWS infrastructure devices
    
    <details markdown=1><summary markdown="span">Answer</summary>
    
    Correct Answer: A
    
    </details>
    
9. Which of the following tasks is required to deploy a PCI-compliant workload on AWS?
    
    - A. Use any AWS service and implement PCI controls at the application layer
    - B. Use an AWS service that is in-scope for PCI compliance and raise an AWS support ticket to enable PCI compliance at the application layer
    - C. Use any AWS service and raise an AWS support ticket to enable PCI compliance on that service
    - D. Use an AWS service that is in scope for PCI compliance and apply PCI controls at the application layer
    
    <details markdown=1><summary markdown="span">Answer</summary>
    
    Correct Answer: D
    
    Explanation: [https://docs.aws.amazon.com/securityhub/latest/userguide/securityhub-pci-controls.html](https://docs.aws.amazon.com/securityhub/latest/userguide/securityhub-pci-controls.html)
    
    </details>
    
10. A company is building an application that requires the ability to send, store, and receive messages between application components. The company has another requirement to process messages in first-in, first-out (FIFO) order. <br/> Which AWS service should the company use?
    
    - A. AWS Step Functions
    - B. Amazon Simple Notification Service (Amazon SNS)
    - C. Amazon Kinesis Data Streams
    - D. Amazon Simple Queue Service (Amazon SQS)
    
    <details markdown=1><summary markdown="span">Answer</summary>
    
    Correct Answer: D
    
    Explanation: [https://aws.amazon.com/sqs/faqs/](https://aws.amazon.com/sqs/faqs/)
    
    </details>
    
11. AnyCompany recently purchased Example Corp. Both companies use AWS resources, and AnyCompany wants a single aggregated bill. <br/> Which option allows AnyCompany to receive a single bill?
    
    - A. Example Corp. must submit a request to its AWS solutions architect or AWS technical account manager to link the accounts and consolidate billing.
    - B. AnyCompany must create a new support case in the AWS Support Center requesting that both bills be combined.
    - C. Send an invitation to join the organization from AnyCompany's AWS Organizations master account to Example Corp.
    - D. Migrate the Example Corp. VPCs, Amazon EC2 instances, and other resources into the AnyCompany AWS account.
    
    <details markdown=1><summary markdown="span">Answer</summary>
    
    Correct Answer: C
    
    Explanation: [https://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/awsaccountbilling-aboutv2.pdf](https://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/awsaccountbilling-aboutv2.pdf)
    
    </details>
    
12. Which tool can be used to create alerts when the actual or forecasted cost of AWS services exceeds a certain threshold?
    
    - A. Cost Explorer
    - B. AWS Budgets
    - C. AWS Cost and Usage Report
    - D. AWS CloudTrail
    
    <details markdown=1><summary markdown="span">Answer</summary>
    
    Correct Answer: B
    
    Explanation: [https://aws.amazon.com/getting-started/hands-on/control-your-costs-free-tier-budgets/](https://aws.amazon.com/getting-started/hands-on/control-your-costs-free-tier-budgets/)
    
    </details>
    
13. A user has limited knowledge of AWS services, but wants to quickly deploy a scalable Node.js application in the AWS Cloud. <br/> Which service should be used to deploy the application?
    
    - A. AWS CloudFormation
    - B. AWS Elastic Beanstalk
    - C. Amazon EC2
    - D. AWS OpsWorks
    
    <details markdown=1><summary markdown="span">Answer</summary>
    
    Correct Answer: B
    
    Explanation: [https://aws.amazon.com/elasticbeanstalk/](https://aws.amazon.com/elasticbeanstalk/)
    
    </details>
    
14. Which AWS Trusted Advisor check is available to all AWS users?
    
    - A. Core checks
    - B. All checks
    - C. Cost optimization checks
    - D. Fault tolerance checks
    
    <details markdown=1><summary markdown="span">Answer</summary>
    
    Correct Answer: A
    
    Explanation: [https://www.amazonaws.cn/en/support/trustedadvisor/faq/#checks](https://www.amazonaws.cn/en/support/trustedadvisor/faq/#checks)
    
    </details>
    
15. A web developer is concerned that a DDoS attack could target an application. <br/> Which AWS services or features can help protect against such an attack? (Choose two.)
    
    - A. AWS Shield
    - B. AWS CloudTrail
    - C. Amazon CloudFront
    - D. AWS Support Center
    - E. AWS Service Health Dashboard
    
    <details markdown=1><summary markdown="span">Answer</summary>
    
    Correct Answer: AC
    
    Explanation: [https://aws.amazon.com/shield/](https://aws.amazon.com/shield/)
    
    </details>
    
16. Which AWS service gives users on-demand, self-service access to AWS compliance control reports?
    
    - A. AWS Config
    - B. Amazon GuardDuty
    - C. AWS Trusted Advisor
    - D. AWS Artifact
    
    <details markdown=1><summary markdown="span">Answer</summary>
    
    Correct Answer: D
    
    Explanation: [https://aws.amazon.com/artifact](https://aws.amazon.com/artifact)
    
    </details>
    
17. A company wants to provide one of its employees with access to Amazon RDS. The company also wants to limit the interaction to only the AWS CLI and AWS software development kits (SDKs). <br/> Which combination of actions should the company take to meet these requirements while following the principles of least privilege? (Choose two.)
    
    - A. Create an IAM user and provide AWS Management Console access only.
    - B. Create an IAM user and provide programmatic access only.
    - C. Create an IAM role and provide AWS Management Console access only.
    - D. Create an IAM policy with administrator access and attach it to the IAM user.
    - E. Create an IAM policy with Amazon RDS access and attach it to the IAM user.
    
    <details markdown=1><summary markdown="span">Answer</summary>
    
    Correct Answer: BE
    
    </details>
    
18. A company has a compliance requirement to record and evaluate configuration changes, as well as perform remediation actions on AWS resources. <br/> Which AWS service should the company use?
    
    - A. AWS Config
    - B. AWS Secrets Manager
    - C. AWS CloudTrail
    - D. AWS Trusted Advisor
    
    <details markdown=1><summary markdown="span">Answer</summary>
    
    Correct Answer: A
    
    Explanation: [https://aws.amazon.com/config/](https://aws.amazon.com/config/)
    
    </details>
    
19. What are the advantages of deploying an application with Amazon EC2 instances in multiple Availability Zones? (Choose two.)
    
    - A. Preventing a single point of failure
    - B. Reducing the operational costs of the application
    - C. Allowing the application to serve cross-region users with low latency
    - D. Increasing the availability of the application
    - E. Increasing the load of the application
    
    <details markdown=1><summary markdown="span">Answer</summary>
    
    Correct Answer: AD
    
    Explanation: [https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-increase-availability.html](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-increase-availability.html)
    
    </details>
    
20. A workload on AWS will run for the foreseeable future by using a consistent number of Amazon EC2 instances. <br/> What pricing model will minimize cost while ensuring that compute resources remain available?
    
    - A. Dedicated Hosts
    - B. On-Demand Instances
    - C. Spot Instances
    - D. Reserved Instances
    
    <details markdown=1><summary markdown="span">Answer</summary>
    
    Correct Answer: D
    
    Explanation: [https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-reserved-instances.html](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-reserved-instances.html)
    
    </details>
    
21. Which tool can be used to identify scheduled changes to the AWS infrastructure?
    
    - A. AWS Personal Health Dashboard
    - B. AWS Trusted Advisor
    - C. Billing Dashboard
    - D. AWS Config
    
    <details markdown=1><summary markdown="span">Answer</summary>
    
    Correct Answer: A
    
    Explanation: [https://aws.amazon.com/premiumsupport/technology/personal-health-dashboard/](https://aws.amazon.com/premiumsupport/technology/personal-health-dashboard/)
    
    </details>
    
22. Which of the following is the customer's responsibility when using Amazon RDS?
    
    - A. Patching the operating system of underlying hardware
    - B. Controlling traffic to and from the database through security groups
    - C. Running backups that enable point-in-time recovery of a DB instance
    - D. Replacing failed DB instances
    
    <details markdown=1><summary markdown="span">Answer</summary>
    
    Correct Answer: B
    
    Explanation: [https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/UsingWithRDS.html](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/UsingWithRDS.html)
    
    </details>
    
23. What is the customer's responsibility when using AWS Lambda?
    
    - A. Operating system configuration
    - B. Application management
    - C. Platform management
    - D. Code encryption
    
    <details markdown=1><summary markdown="span">Answer</summary>
    
    Correct Answer: B
    
    Explanation: [https://aws.amazon.com/lambda/security-overview-of-aws-lambda/](https://aws.amazon.com/lambda/security-overview-of-aws-lambda/)
    
    </details>
    
24. A company wants to be notified when its AWS Cloud costs or usage exceed defined thresholds. <br/> Which AWS service will support these requirements?
    
    - A. AWS Budgets
    - B. Cost Explorer
    - C. AWS CloudTrail
    - D. Amazon Macie
    
    <details markdown=1><summary markdown="span">Answer</summary>
    
    Correct Answer: A
    
    Explanation: [https://aws.amazon.com/aws-cost-management/aws-budgets/](https://aws.amazon.com/aws-cost-management/aws-budgets/)
    
    </details>
    
25. Which AWS service provides the ability to host a NoSQL database in the AWS Cloud?
    
    - A. Amazon Aurora
    - B. Amazon DynamoDB
    - C. Amazon RDS
    - D. Amazon Redshift
    
    <details markdown=1><summary markdown="span">Answer</summary>
    
    Correct Answer: B
    
    Explanation: [https://aws.amazon.com/nosql/](https://aws.amazon.com/nosql/)
    
    </details>
    
26. Which AWS service allows customers to purchase unused Amazon EC2 capacity at an often discounted rate?
    
    - A. Reserved Instances
    - B. On-Demand Instances
    - C. Dedicated Instances
    - D. Spot Instances
    
    <details markdown=1><summary markdown="span">Answer</summary>
    
    Correct Answer: D
    
    Explanation: [https://aws.amazon.com/ec2/spot/](https://aws.amazon.com/ec2/spot/)
    
    </details>
    
27. Which AWS service or feature requires an internet service provider (ISP) and a colocation facility to be implemented?
    
    - A. AWS VPN
    - B. Amazon Connect
    - C. AWS Direct Connect
    - D. Internet gateway
    
    <details markdown=1><summary markdown="span">Answer</summary>
    
    Correct Answer: C
    
    Explanation: [https://aws.amazon.com/directconnect/partners/](https://aws.amazon.com/directconnect/partners/)
    
    </details>
    
28. Which AWS services offer compute capabilities? (Choose two.)
    
    - A. Amazon EC2
    - B. Amazon S3
    - C. Amazon Elastic Block Store (Amazon EBS)
    - D. Amazon Cognito
    - E. AWS Lambda
    
    <details markdown=1><summary markdown="span">Answer</summary>
    
    Correct Answer: AE
    
    Explanation: [https://docs.aws.amazon.com/whitepapers/latest/aws-overview/compute-services.html](https://docs.aws.amazon.com/whitepapers/latest/aws-overview/compute-services.html)
    
    </details>
    
29. Which AWS service can be used to privately store and manage versions of source code?
    
    - A. AWS CodeBuild
    - B. AWS CodeCommit
    - C. AWS CodePipeline
    - D. AWS CodeStar
    
    <details markdown=1><summary markdown="span">Answer</summary>
    
    Correct Answer: B
    
    Explanation: [https://docs.aws.amazon.com/codecommit/latest/userguide/welcome.html](https://docs.aws.amazon.com/codecommit/latest/userguide/welcome.html)
    
    </details>
    
30. Which AWS service should a cloud practitioner use to identify security vulnerabilities of an AWS account?
    
    - A. AWS Secrets Manager
    - B. Amazon Cognito
    - C. Amazon Macie
    - D. AWS Trusted Advisor
    
    <details markdown=1><summary markdown="span">Answer</summary>
    
    Correct Answer: D
    
    Explanation: [https://www.coalfire.com/the-coalfire-blog/march-2019/aws-trusted-advisor-for-security-compliance](https://www.coalfire.com/the-coalfire-blog/march-2019/aws-trusted-advisor-for-security-compliance)
    
    </details>
    
31. A company wants to ensure its infrastructure is designed for fault tolerance and business continuity in the event of an environmental disruption. <br/> Which AWS infrastructure component should the company replicate across?
    
    - A. Edge locations
    - B. Availability Zones
    - C. Regions
    - D. Amazon Route 53
    
    <details markdown=1><summary markdown="span">Answer</summary>
    
    Correct Answer: B
    
    Explanation: [https://d36cz9buwru1tt.cloudfront.net/AWS_Building_Fault_Tolerant_Applications.pdf](https://d36cz9buwru1tt.cloudfront.net/AWS_Building_Fault_Tolerant_Applications.pdf)
    
    </details>
    
32. Which AWS service or feature is used to send both text and email messages from distributed applications?
    
    - A. Amazon Simple Notification Service (Amazon SNS)
    - B. Amazon Simple Email Service (Amazon SES)
    - C. Amazon CloudWatch alerts
    - D. Amazon Simple Queue Service (Amazon SQS)
    
    <details markdown=1><summary markdown="span">Answer</summary>
    
    Correct Answer: A
    
    Explanation: [https://aws.amazon.com/sns/faqs/](https://aws.amazon.com/sns/faqs/)
    
    </details>
    
33. Which AWS Cloud design principles can help increase reliability? (Choose two.)
    
    - A. Using monolithic architecture
    - B. Measuring overall efficiency
    - C. Testing recovery procedures
    - D. Adopting a consumption model
    - E. Automatically recovering from failure
    
    <details markdown=1><summary markdown="span">Answer</summary>
    
    Correct Answer: CE
    
    Explanation: [https://wa.aws.amazon.com/wat.pillar.reliability.en.html](https://wa.aws.amazon.com/wat.pillar.reliability.en.html)
    
    </details>
    
34. A company is planning to launch an ecommerce site in a single AWS Region to a worldwide user base. <br/> Which AWS services will allow the company to reach users and provide low latency and high transfer speeds? (Choose two.)
    
    - A. Application Load Balancer
    - B. AWS Global Accelerator
    - C. AWS Direct Connect
    - D. Amazon CloudFront
    - E. AWS Lambda
    
    <details markdown=1><summary markdown="span">Answer</summary>
    
    Correct Answer: BD
    
    Explanation: [https://aws.amazon.com/cloudfront/faqs/](https://aws.amazon.com/cloudfront/faqs/)
    
    </details>
    
35. A company wants to connect to AWS over a private, low-latency connection from its remote office. <br/> What is the recommended method to meet these requirements?
    
    - A. Create a VPN tunnel
    - B. Connect across the public internet
    - C. Use VPC peering to create a connection.
    - D. Use AWS Direct Connect.
    
    <details markdown=1><summary markdown="span">Answer</summary>
    
    Correct Answer: D
    
    Explanation: [https://aws.amazon.com/getting-started/projects/connect-data-center-to-aws/](https://aws.amazon.com/getting-started/projects/connect-data-center-to-aws/)
    
    </details>
    
36. Which AWS service can be used to retrieve compliance reports on demand?
    
    - A. AWS Secrets Manager
    - B. AWS Artifact
    - C. AWS Security Hub
    - D. AWS Certificate Manager
    
    <details markdown=1><summary markdown="span">Answer</summary>
    
    Correct Answer: B
    
    Explanation: [https://aws.amazon.com/artifact/](https://aws.amazon.com/artifact/)
    
    </details>
    
37. A company has an AWS-hosted website located behind an Application Load Balancer. The company wants to safeguard the website from SQL injection or cross-site scripting. <br/> Which AWS service should the company use?
    
    - A. Amazon GuardDuty
    - B. AWS WAF
    - C. AWS Trusted Advisor
    - D. Amazon Inspector
    
    <details markdown=1><summary markdown="span">Answer</summary>
    
    Correct Answer: B
    
    Explanation: [https://aws.amazon.com/waf/faq/](https://aws.amazon.com/waf/faq/)
    
    </details>
    
38. How should a web application be deployed to ensure high availability in the AWS Cloud?
    
    - A. Deploy multiple instances of the application in multiple Availability Zones.
    - B. Deploy multiple instances of the application in a single Availability Zone.
    - C. Deploy the application to a compute-optimized Amazon EC2 instance in a single Availability Zone.
    - D. Deploy the application in one Amazon EC2 instance in an Auto Scaling group.
    
    <details markdown=1><summary markdown="span">Answer</summary>
    
    Correct Answer: A
    
    Explanation: [https://www.betsol.com/blog/how-to-make-high-availability-web-applications-on-amazon-web-services/](https://www.betsol.com/blog/how-to-make-high-availability-web-applications-on-amazon-web-services/)
    
    </details>
    
39. A company is running a self-managed Oracle database directly on Amazon EC2 for its steady-state database. The company wants to reduce compute costs. <br/> Which option should the company use to maximize savings over a 3-year term?
    
    - A. EC2 Dedicated Instances
    - B. EC2 Spot Instances
    - C. EC2 Reserved Instances
    - D. EC2 On-Demand Instances
    
    <details markdown=1><summary markdown="span">Answer</summary>
    
    Correct Answer: C
    
    Explanation: [https://aws.amazon.com/choosing-a-cloud-platform/](https://aws.amazon.com/choosing-a-cloud-platform/)
    
    </details>
    
40. An external auditor has requested that a company provide a list of all its IAM users, including the status of users' credentials and access keys. <br/> What it the SIMPLEST way to provide this information?
    
    - A. Create an IAM user account for the auditor, granting the auditor administrator permissions.
    - B. Take a screenshot of each user's page in the AWS Management Console, then provide the screenshots to the auditor.
    - C. Download the IAM credential report, then provide the report to the auditor.
    - D. Download the AWS Trusted Advisor report, then provide the report to the auditor.
    
    <details markdown=1><summary markdown="span">Answer</summary>
    
    Correct Answer: C
    
    Explanation: [https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_getting-report.html](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_getting-report.html)
    
    </details>
    
41. What are the benefits of consolidated billing for AWS Cloud services? (Choose two.)
    
    - A. Volume discounts
    - B. A minimal additional fee for use
    - C. One bill for multiple accounts
    - D. Installment payment options
    - E. Custom cost and usage budget creation
    
    <details markdown=1><summary markdown="span">Answer</summary>
    
    Correct Answer: AC
    
    Explanation: [https://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/consolidated-billing.html](https://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/consolidated-billing.html)
    
    </details>
    
42. A company is expecting a short-term spike in internet traffic for its application. During the traffic increase, the application cannot be interrupted. The company also needs to minimize cost and maximize flexibility. <br/> Which Amazon EC2 instance type should the company use to meet these requirements?
    
    - A. On-Demand Instances
    - B. Spot Instances
    - C. Reserved Instances
    - D. Dedicated Hosts
    
    <details markdown=1><summary markdown="span">Answer</summary>
    
    Correct Answer: A
    
    Explanation: [https://aws.amazon.com/ec2/faqs/](https://aws.amazon.com/ec2/faqs/)
    
    </details>
    
43. A company wants to track AWS resource configuration changes for compliance reasons. <br/> Which AWS feature can be used to meet this requirement?
    
    - A. AWS Cost and Usage Report
    - B. AWS Organizations service control policies (SCPs)
    - C. AWS Config rules
    - D. VPC Flow Logs
    
    <details markdown=1><summary markdown="span">Answer</summary>
    
    Correct Answer: C
    
    Explanation: [https://aws.amazon.com/config/](https://aws.amazon.com/config/)
    
    </details>
    
44. A company is building an application that needs to deliver images and videos globally with minimal latency. <br/> Which approach can the company use to accomplish this in a cost effective manner?
    
    - A. Deliver the content through Amazon CloudFront.
    - B. Store the content on Amazon S3 and enable S3 cross-region replication.
    - C. Implement a VPN across multiple AWS Regions.
    - D. Deliver the content through AWS PrivateLink.
    
    <details markdown=1><summary markdown="span">Answer</summary>
    
    Correct Answer: A
    
    Explanation: [https://aws.amazon.com/blogs/industries/how-to-build-a-global-scalable-low-latency-and-secure-machine-learning-medical-imaging-analysis-platform-on-aws/](https://aws.amazon.com/blogs/industries/how-to-build-a-global-scalable-low-latency-and-secure-machine-learning-medical-imaging-analysis-platform-on-aws/)
    
    </details>
    
45. The AWS IAM best practice for granting least privilege is to:
    
    - A. apply an IAM policy to an IAM group and limit the size of the group.
    - B. require multi-factor authentication (MFA) for all IAM users.
    - C. require each IAM user who has different permissions to have multiple passwords.
    - D. apply an IAM policy only to IAM users who require it.
    
    <details markdown=1><summary markdown="span">Answer</summary>
    
    Correct Answer: D
    
    Explanation: [https://kirkpatrickprice.com/blog/best-practices-for-privilege-management-in-aws/](https://kirkpatrickprice.com/blog/best-practices-for-privilege-management-in-aws/)
    
    </details>
    
46. Which cloud computing benefit does AWS demonstrate with its ability to offer lower variable costs as a result of high purchase volumes?
    
    - A. Pay-as-you-go pricing
    - B. High availability
    - C. Global reach
    - D. Economies of scale
    
    <details markdown=1><summary markdown="span">Answer</summary>
    
    Correct Answer: D
    
    Explanation: [https://innovationtactics.com/amazon-business-model-amazon-web-services/](https://innovationtactics.com/amazon-business-model-amazon-web-services/)
    
    </details>
    
47. A pharmaceutical company operates its infrastructure in a single AWS Region. The company has thousands of VPCs in a various AWS accounts that it wants to interconnect. <br/> Which AWS service or feature should the company use to help simplify management and reduce operational costs?
    
    - A. VPC endpoint
    - B. AWS Direct Connect
    - C. AWS Transit Gateway
    - D. VPC peering
    
    <details markdown=1><summary markdown="span">Answer</summary>
    
    Correct Answer: C
    
    Explanation: [https://d1.awsstatic.com/whitepapers/building-a-scalable-and-secure-multi-vpc-aws-network-infrastructure.pdf](https://d1.awsstatic.com/whitepapers/building-a-scalable-and-secure-multi-vpc-aws-network-infrastructure.pdf)
    
    </details>
    
48. How can AWS enable a company to control expenses as an application's usage changes unpredictably?
    
    - A. AWS will refund the cost difference if a customer moves to larger servers.
    - B. The application can be built to scale up or down automatically as resources are needed
    - C. Spot instances will automatically be used if the price is lower than on-demand instances.
    - D. Amazon CloudWatch will automatically predict what resources are needed.
    
    <details markdown=1><summary markdown="span">Answer</summary>
    
    Correct Answer: B
    
    </details>
    
49. Which AWS service or feature can be used to prevent SQL injection attacks?
    
    - A. Security groups
    - B. Network ACLs
    - C. AWS WAF
    - D. IAM policy
    
    <details markdown=1><summary markdown="span">Answer</summary>
    
    Correct Answer: C
    
    Explanation:  
      
    [https://docs.aws.amazon.com/waf/latest/developerguide/classic-web-acl-sql-conditions.html](https://docs.aws.amazon.com/waf/latest/developerguide/classic-web-acl-sql-conditions.html)
    
    </details>
    

  

  

A company has deployed applications on Amazon EC2 instances. The company needs to assess application vulnerabilities and must identify infrastructure deployments that do not meet best practices.

Which AWS service can the company use to meet these requirements?

- A. AWS Trusted Advisor
- B. Amazon Inspector
- C. AWS Config
- D. Amazon GuardDuty

answer is C

  

  

A company has a centralized group of users with large file storage requirements that have exceeded the space available on premises. The company wants to extend its file storage capabilities for this group while retaining the performance benefit of sharing content locally.

What is the MOST operationally efficient AWS solution for this scenario?

- A. Create an Amazon S3 bucket for each user. Mount each bucket by using an S3 file system mounting utility.
- B. Configure and deploy an AWS Storage Gateway file gateway. Connect each user’s workstation to the file gateway. **Most Voted**
- C. Move each user’s working environment to Amazon WorkSpaces. Set up an Amazon WorkDocs account for each user.
- D. Deploy an Amazon EC2 instance and attach an Amazon Elastic Block Store (Amazon EBS) Provisioned IOPS volume. Share the EBS volume directly with the users.

[Hide Solution](https://www.examtopics.com/exams/amazon/aws-certified-cloud-practitioner-clf-c02/view/#)

[Discussion](https://www.examtopics.com/exams/amazon/aws-certified-cloud-practitioner-clf-c02/view/#)   **[18](https://www.examtopics.com/exams/amazon/aws-certified-cloud-practitioner-clf-c02/view/#)**

**Correct Answer:** _B_

  

Which AWS services or tools can identify rightsizing opportunities for Amazon EC2 instances? (Choose two.)

- A. AWS Cost Explorer **Most Voted**
- B. AWS Billing Conductor
- C. Amazon CodeGuru
- D. Amazon SageMaker
- E. AWS Compute Optimize

  

A company wants to manage deployed IT services and govern its infrastructure as code (IaC) templates.

Which AWS service will meet this requirement?

- A. AWS Resource Explorer
- B. AWS Service Catalog **Most Voted**
- C. AWS Organizations
- D. AWS Systems Manager

[Hide Solution](https://www.examtopics.com/exams/amazon/aws-certified-cloud-practitioner-clf-c02/view/2/#)

[Discussion](https://www.examtopics.com/exams/amazon/aws-certified-cloud-practitioner-clf-c02/view/2/#)   **[24](https://www.examtopics.com/exams/amazon/aws-certified-cloud-practitioner-clf-c02/view/2/#)**

**Correct Answer:** _B_ [🗳️](https://www.examtopics.com/exams/amazon/aws-certified-cloud-practitioner-clf-c02/view/2/#)



![[Pasted image 20250130235719.png]]

![[Pasted image 20250131000427.png]]

![[Pasted image 20250131000546.png]]![[Pasted image 20250131001540.png]]
![[Pasted image 20250131002401.png]]
![[Pasted image 20250131004858.png]]![[Pasted image 20250131005343.png]]![[Pasted image 20250131005440.png]]![[AWS/assets/TOP 40 questions/Pasted image 20250131005710.png]]
![[Pasted image 20250131011008.png]]
![[Pasted image 20250131011633.png]]
![[AWS/assets/TOP 40 questions/Pasted image 20250131011922.png]]****![[Pasted image 20250131012342.png]]
![[Pasted image 20250131013413.png]]![[Pasted image 20250131013606.png]]
![[Pasted image 20250131014720.png]]
![[Pasted image 20250131015741.png]]![[Pasted image 20250131015947.png]]![[Pasted image 20250131020211.png]]![[Pasted image 20250131181824.png]]![[Pasted image 20250131182131.png]]![[Pasted image 20250131182622.png]]![[Pasted image 20250131182912.png]]![[Pasted image 20250131183537.png]]![[Pasted image 20250131190604.png]]![[Pasted image 20250131190815.png]]
![[Pasted image 20250131192744.png]]![[Pasted image 20250131193147.png]]![[Pasted image 20250131193947.png]]![[Pasted image 20250131195004.png]]![[Pasted image 20250131195145.png]]![[Pasted image 20250131200711.png]]![[Pasted image 20250131201016.png]]![[Pasted image 20250131201306.png]]
![[Pasted image 20250131201506.png]]![[Pasted image 20250131201543.png]]![[Pasted image 20250131201951.png]]![[Pasted image 20250131202845.png]]![[Pasted image 20250131202951.png]]![[Pasted image 20250131203051.png]]![[Pasted image 20250131203200.png]]![[Pasted image 20250131203627.png]]![[Pasted image 20250131203752.png]]
![[AWS/assets/TOP 40 questions/Pasted image 20250131203954.png]]![[AWS/assets/TOP 40 questions/Pasted image 20250131204219.png]]![[AWS/assets/TOP 40 questions/Pasted image 20250131204700.png]]![[AWS/assets/TOP 40 questions/Pasted image 20250131205015.png]]![[AWS/assets/TOP 40 questions/Pasted image 20250131205444.png]]![[AWS/assets/TOP 40 questions/Pasted image 20250131205838.png]]![[AWS/assets/TOP 40 questions/Pasted image 20250203161919.png]]![[AWS/assets/TOP 40 questions/Pasted image 20250203162311.png]]![[AWS/assets/TOP 40 questions/Pasted image 20250203162929.png]]![[AWS/assets/TOP 40 questions/Pasted image 20250203163602.png]]![[AWS/assets/TOP 40 questions/Pasted image 20250203164326.png]]![[AWS/assets/TOP 40 questions/Pasted image 20250203165417.png]]![[AWS/assets/TOP 40 questions/Pasted image 20250203165551.png]]
![[Pasted image 20250131203954 1.png]]![[Pasted image 20250131204219 1.png]]![[Pasted image 20250131204700 1.png]]![[Pasted image 20250131205015 1.png]]![[Pasted image 20250131205444 1.png]]![[Pasted image 20250131205838 1.png]]![[Pasted image 20250203161919 1.png]]![[Pasted image 20250203162311 1.png]]![[Pasted image 20250203162929 1.png]]![[Pasted image 20250203163602 1.png]]![[Pasted image 20250203164326 1.png]]![[Pasted image 20250203165417 1.png]]![[Pasted image 20250203165551 1.png]]![[Pasted image 20250203170311.png]]![[Pasted image 20250203170622.png]]![[Pasted image 20250203170756.png]]