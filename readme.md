Study Group & Peer Tutoring Platform
A cloud-native, microservices-based SaaS solution designed to bridge the gap between students seeking academic help and those offering it. This platform leverages AWS to ensure high availability, scalability, and a seamless CI/CD experience.
🚀 Project Overview
Traditional student networking often suffers from fragmented scheduling and discovery issues. This project solves those bottlenecks by moving away from monolithic designs to a Microservices Architecture deployed on Amazon Web Services (AWS).
Key Features
•	Microservices Design: Independent services for Users, Tutoring, and Groups.
•	Zero-Downtime Updates: Implemented via a Blue-Green Deployment strategy.
•	Scalability: Services scale independently using AWS Auto Scaling to handle peak exam seasons.
•	Security: Environment-based configuration and IAM roles to enforce the principle of least privilege.
________________________________________
🏗 System Architecture
The infrastructure is built to be robust and secure, utilizing a custom VPC with public and private subnets.
•	Frontend: A modern, responsive interface (React/Bootstrap) accessible via an Application Load Balancer (ALB).
•	Backend: Node.js/Express microservices containerized with Docker.
•	Database: Amazon RDS (PostgreSQL/MySQL) and DynamoDB hosted in private subnets for maximum security.
•	Orchestration: Amazon ECS (Elastic Container Service) managing container lifecycles.
________________________________________
💻 Tech Stack
Component	Technology
Frontend	HTML5, CSS3 (Bootstrap), JavaScript (React)
Backend	Node.js, Express.js
Containerization	Docker
Cloud Provider	AWS (VPC, ECS, RDS, ALB, ECR)
CI/CD	AWS CodePipeline, CodeCommit, CodeBuild, CodeDeploy
Monitoring	Amazon CloudWatch
________________________________________
🛠 Installation & Local Setup
Prerequisites
•	Node.js (v16+)
•	Docker Desktop
•	AWS CLI configured (for cloud deployment)
1. Clone the Repository
Bash
https://github.com/Hazira-Azam/Study-Group-Peer-Tutoring-Platform
cd tutoring-platform
2. Backend Setup (Example: User Service)
Bash
cd backend/user-service
npm install
# Create a .env file and add your RDS credentials
npm start
3. Frontend Setup
Bash
cd frontend
npm install
npm start
________________________________________
🚢 CI/CD Pipeline & Deployment
The platform uses a fully automated pipeline to ensure that every code push is tested and deployed without interrupting the student learning cycle.
1.	Source: Code is pushed to AWS CodeCommit.
2.	Build: AWS CodeBuild packages the code into a Docker image and pushes it to Amazon ECR.
3.	Deploy: AWS CodeDeploy triggers a Blue-Green Deployment on ECS.
o	Green: The new version is tested.
o	Blue: The current live version.
o	Traffic is shifted only after the Green environment passes health checks.
________________________________________
🔒 Security & Optimization
•	Private Subnets: All database instances and backend tasks are hidden from the public internet.
•	Environment Variables: Sensitive data (API keys, DB passwords) are never hardcoded; they are managed via AWS Secrets Manager or .env files.
•	IAM Roles: Precise permissions assigned to ECS tasks to limit access to AWS resources.
________________________________________
👥 Contributors
•	Hazira Azam - BSSE23019
•	Areeba Shahbaz - BSSE23097

