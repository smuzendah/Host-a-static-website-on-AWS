## Hosting a Static Website on AWS

This repository contains scripts and configuration files for deploying a static HTML web application on Amazon Web Services (AWS) infrastructure. The deployment utilizes various AWS services and best practices in DevOps and cloud computing.

### Overview

The project aims to host a static HTML web application on AWS infrastructure, ensuring reliability, security, scalability, and fault tolerance. Below is a summary of the key components and configurations used in the deployment:

1. **Virtual Private Cloud (VPC)**:
   - Configured a VPC with public and private subnets across multiple availability zones for enhanced fault tolerance.

2. **Internet Gateway**:
   - Deployed an Internet Gateway to facilitate connectivity between VPC instances and the wider Internet.

3. **Security Groups**:
   - Established Security Groups as a network firewall mechanism to control traffic to EC2 instances.

4. **Availability Zones**:
   - Leveraged multiple Availability Zones to enhance system reliability and fault tolerance.

5. **Subnets**:
   - Utilized Public Subnets for infrastructure components like the NAT Gateway and Application Load Balancer.
   - Positioned web servers (EC2 instances) within Private Subnets for enhanced security.

6. **EC2 Instance Connect Endpoint**:
   - Implemented EC2 Instance Connect Endpoint for secure connections to assets within both public and private subnets.

7. **NAT Gateway**:
   - Enabled instances in both private Application and Data subnets to access the Internet via the NAT Gateway.

8. **Web Hosting**:
   - Hosted the static website on EC2 Instances.

9. **Load Balancing and Auto Scaling**:
   - Employed an Application Load Balancer and a target group for evenly distributing web traffic to an Auto Scaling Group of EC2 instances across multiple Availability Zones.
   - Utilized an Auto Scaling Group to automatically manage EC2 instances, ensuring website availability, scalability, fault tolerance, and elasticity.

10. **Version Control and Collaboration**:
    - Stored web files on GitHub for version control and collaboration.

11. **Security**:
    - Secured application communications using a Certificate Manager.

12. **Monitoring and Alerting**:
    - Configured Simple Notification Service (SNS) to alert about activities within the Auto Scaling Group.

13. **Domain Name Management**:
    - Registered the domain name and set up a DNS record using Route 53.

### Deployment Script

The provided deployment script automates the setup of the web application environment on an EC2 instance. It performs the following tasks:

- Updates all installed packages to their latest versions.
- Installs Apache HTTP Server.
- Clones the project GitHub repository.
- Copies all files, including hidden ones, from the cloned repository to the Apache web root.
- Cleans up unnecessary files.
- Enables the Apache HTTP Server to start automatically at system boot.
- Starts the Apache HTTP Server to serve web content.

### Usage

To deploy the static website on AWS using the provided script:

1. Launch an EC2 instance with appropriate IAM roles and permissions.
2. SSH into the EC2 instance.
3. Run the provided deployment script.
4. Access the website using the public DNS or domain name associated with the EC2 instance.

### Repository Structure

- **README.md**: This readme file providing an overview of the project and instructions for deployment.
- **deploy_script.sh**: Bash script for deploying the static website on an EC2 instance.
- **diagram.png**: Reference diagram illustrating the AWS architecture for hosting the static website.
- **.gitignore**: Specifies intentionally untracked files to ignore.
- **/var/www/html/**: Directory containing web content served by the Apache HTTP Server.

### Disclaimer

This project is intended for educational and demonstration purposes. Ensure proper AWS account configuration and adhere to AWS best practices before deploying any production workloads.

For any questions or issues, please contact [sylvester.muzendah@gmail.com].
