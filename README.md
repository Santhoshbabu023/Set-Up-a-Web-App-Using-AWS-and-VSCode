# AWS EC2 Java Web App with VS Code

## Project Overview
This project sets up an **AWS EC2 instance**, connects to it remotely via **VS Code using SSH**, and installs **Maven and Java**. A basic Java web application is generated using Maven, creating a foundation for future **DevOps and cloud-based development**.

## Features
- **Launch an AWS EC2 instance** for cloud-based hosting.
- **Set up SSH access** for secure remote management.
- **Install Maven & Java** to manage project dependencies.
- **Generate a Java web app** using Maven archetypes.
- **Use VS Code Remote - SSH** for seamless development.
- **Deploy and test a JSP-based web app**.

## Prerequisites
- **AWS Account** with permissions to create an EC2 instance.
- **VS Code** with the **Remote - SSH extension** installed.
- **SSH Key Pair** for authentication.
- **Basic knowledge of Java & Maven**.

## Setup Instructions
### 1. Launch an EC2 Instance
1. Log in to AWS and navigate to **EC2**.
2. Create a new instance using **Amazon Linux** or **Ubuntu**.
3. Enable SSH (port 22) in **Security Groups**.
4. Download the **.pem key pair** for authentication.

### 2. Connect to EC2 via SSH
Run the following command in the terminal:

ssh -i /path/to/key.pem ec2-user@your-ec2-public-ip


### 3. Install Maven & Java
For Amazon Linux:

sudo yum update -y
sudo yum install maven -y

For Ubuntu:

sudo apt update -y
sudo apt install maven -y

Verify installation:

mvn -v


### 4. Generate a Java Web App
Run:

mvn archetype:generate \
   -DgroupId=com.nextwork.app \
   -DartifactId=nextwork-web-project \
   -DarchetypeArtifactId=maven-archetype-webapp \
   -DinteractiveMode=false

Navigate into the project directory:

cd nextwork-web-project

### 5. Set Up VS Code for Remote Development
1. Install **Remote - SSH** extension in VS Code.
2. Open VS Code and **Connect to Host...** using your EC2 instance.
3. Navigate to your project folder and start coding.

### 6. Explore the Project Structure
- **`src/`** – Java source code and servlets.
- **`webapp/`** – JSP, HTML, CSS, and JS files.
- **`pom.xml`** – Maven build file.

### 7. Deploy and Test
Use **Tomcat** or another server to deploy your web app:

mvn package

Start the server and access your app in a browser.

## Next Steps
- Automate deployments using **CI/CD with Jenkins**.
- Integrate **Docker & Kubernetes** for containerized deployments.
- Enhance security and scalability in **AWS infrastructure**.
