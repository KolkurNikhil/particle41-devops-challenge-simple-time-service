# Flask IP and Timestamp Application

## 📄 Overview
This Flask application returns the client's IP address and the current UTC timestamp in JSON format. It is containerized using Docker for ease of deployment and scalability.

---

## 🛠️ Prerequisites

### Local Environment
- Docker installed on your system.
- Internet connectivity to pull base images and dependencies.

### AWS EC2 Instance
- An active AWS account.
- EC2 instance running a Linux-based OS (e.g., Ubuntu).
- Security group configured to allow inbound traffic on port `5000`.
- SSH access to the EC2 instance.

---

## 📁 Project Structure

📁 Project Structure
project-directory/
├── app.py
├── requirements.txt
├── Dockerfile
└── README.md


---

## 🐳 Dockerization

### Building the Docker Image
Execute the following command in the project directory:
```bash
docker build -t knikhil999/simpletimeservice .


🚀 Deployment Instructions
Building the Docker Image
Execute the following command in the project directory:​
docker build -t knikhil999/simpletimeservice .
Running the Docker Container
Run the container in detached mode and map port 5000:​
docker run -d -p 5000:5000 flask-ip-timestamp

🌐 Accessing the Application
Local Access
Navigate to http://localhost:5000 in your web browser.

Remote Access (EC2)
Navigate to http://<EC2-Public-IP>:5000 in your web browser. Ensure that:

The EC2 instance's security group allows inbound traffic on port 5000.
The application is running, and the Docker container is active.
🚀 Deployment Instructions
Step 1: Launch EC2 Instance
Log in to your AWS account.
Launch an EC2 instance with a Linux-based OS (e.g., Ubuntu).
Configure the security group to allow inbound traffic on port 5000 (Custom TCP Rule).
Step 2: Install Docker on EC2
SSH into your EC2 instance:
bash
ssh -i <your-key-file.pem> ubuntu@<EC2-Public-IP>
Update the package repository:
bash
sudo apt update
Install Docker:
bash
sudo apt install docker.io -y
Verify Docker installation:
bash
docker --version
Step 3: Deploy the Flask Application
Pull the application code or clone the repository:
bash
git clone https://github.com/KolkurNikhil/particle41-devops-challenge-simple-time-service.git
cd particle41-devops-challenge-simple-time-service
Build the Docker image:
bash
docker build -t knikhil999/simpletimeservice .
Run the Docker container:
bash
docker run -d -p 5000:5000 knikhil999/simpletimeservice
Step 4: Test the Deployment
Access the application from your browser:
Local: http://localhost:5000
Remote: http://<EC2-Public-IP>:5000
Test with curl:
bash
curl http://<EC2-Public-IP>:5000
Example Response:

JSON
{
  "ip": "127.0.0.1",
  "timestamp": "2025-04-15T07:00:21.254951Z"
}
🧪 Testing the Application
Send a GET request to the root endpoint:

bash
curl http://localhost:5000
Example Response:

JSON
{
  "ip": "127.0.0.1",
  "timestamp": "2025-04-15T07:00:21.254951Z"
}

