# AnimeFlix
Netflix for Anime

# Motivation
This post is about creating an application similar to Netflix but for Anime only on both AWS and Azure separately. We will be using most of the services and integrate them together to create two separate applications working on their own cloud platform. Our application will be globally accessible and easy to use fast load time with static content delivered by CDN of AWS and Azure. Our application will be deployed in three parts of the world America, Europe, and Asia with restrictive development VM's and an expected billing report.

# Architecture

## AWS
![awsarchitecture](https://user-images.githubusercontent.com/13358738/123792963-f1822e00-d900-11eb-827b-72e920ba6b11.png)

## Azure
![azurearchitecture](https://user-images.githubusercontent.com/13358738/123792979-f515b500-d900-11eb-8071-84e40c9d5a94.png)

# Prerequisites
1. AWS RDS
2. AWS S3
3. AWS CloudFront
4. AWS EC2
5. AWS AMI
6. Elastic IP
7. Route53
8. AWS VPC
9. Azure MySQL Server
10. Azure Storage Accounts
11. Azure CDN
12. Azure Virtual Machine
13. Azure Shared Gallery
14. Azure App Service
15. Azure Traffic Manager
16. Azure DNS Zones
17. Azure VNet


# Steps
1 Follow these commands to run the application
```bash
git clone git@github.com:codexponent/animeflix.git

# # For backend
cd backend
pip install -r requirements.txt
pytrhon main.py

# # For Frontend
cd frontend/
npm install
npm run start
```
2. Configuration (config.ini for flask):
```bash
[MYSQL]
database = 
host = 
user = 
password =
```
3. Configuration (config.json for frontend [src/]):
```bash
{
    "vid_1": <CDN-Link-for-AWS-Azure>,
    "vid_2": <CDN-Link-for-AWS-Azure>,
    "vid_3": <CDN-Link-for-AWS-Azure>,
    "vid_4": <CDN-Link-for-AWS-Azure>,
    "vid_5": <CDN-Link-for-AWS-Azure>,
    "vid_6": <CDN-Link-for-AWS-Azure>
  }
```
4. I also have a Dockerfile for convienence
```bash
docker run -exec -it -p 80:80 -p 5000:5000 -p 3000:3000 --name webserver <image-here>
```
5. Crontab reboot script
```bash
#!/bin/bash
sudo docker stop webserver
sudo docker rm webserver
sudo docker run -exec -it -p 80:80 -p 5000:5000 -p 3000:3000 --name webserver <image-name>

(crontab -l 2>/dev/null; echo "@reboot <location-of-your-above-script>") | crontab -

```

