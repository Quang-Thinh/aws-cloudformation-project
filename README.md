# aws-cloudformation-project
CloudFront URL:
👉 https://d21k0wyeaaeeqs.cloudfront.net/

Với vai trò DevOps Engineer tôi chuyển ứng dụng từ local development sang production trên AWS Cloud.

**Giai đoạn 1:** 

Dựng môi trường deploy trên Linux cho app.

Dựng môi trường deploy trên Linux với production-ready config.

Database Integration: Config kết nối PostgreSQL trong linux environment.


**Giai đoạn 2:**

*Mục tiêu:* Dựng hạ tầng production trên AWS

*Network Infrastructure:*

	VPC: 3-tier architecture (Public, Private App, Private DB)
	
	Subnets: Multi-AZ deployment cho high availability
	
	Security: Security Groups, NACLs, và proper network isolation
	
	Connectivity: NAT Gateway, Internet Gateway, VPC Endpoints
	
*Compute & Storage:*

	EC2: Ec2 servers with
	
	Lauch template:
	
	RDS PostgreSQL: Managed database với Multi-AZ
	
	AMI Builder: Bulding ami with backend application
	
	ASG: Autoscaling group with health check
	
	Loadbalancing
	
*Security & Configuration:*

	Secrets Manager: Database credentials
	
	Parameter Store: Application configuration
	
	IAM Roles: Least privilege access cho services
	
  
**Giai đoạn 3:**

*Build AMI Process (backend):*

	Developer push code to github
	
	Developer rerun AMI builder pipeline to generate new AMI
	
	AMI process phải được trigger lần đâu khi resource được tạo và phải đồng bộ status với cloudformation
	
  
**Giai đoạn 4:**

*Mục tiêu:* Production-ready domain và security

*Requirements:*

	Certificate Manager: SSL/TLS certificates
	
	Application Load Balancer: HTTP termination và traffic distribution
	
	CloudFront: CDN cho Frontend image (optional)
	
