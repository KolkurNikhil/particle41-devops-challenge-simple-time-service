Flask IP and Timestamp Application
📄 Overview
This Flask application returns the client's IP address and the current UTC timestamp in JSON format. It's containerized using Docker for ease of deployment and scalability.​

🛠️ Prerequisites
Local Environment
Docker installed on your system.

Internet connectivity to pull base images and dependencies.​

AWS EC2 Instance
An active AWS account.

EC2 instance running a Linux-based OS (e.g., Ubuntu).

Security group configured to allow inbound traffic on port 5000.

SSH access to the EC2 instance.​
Code Maven

📁 Project Structure
project-directory/
├── app.py
├── requirements.txt
├── Dockerfile
└── README.md
🐳 Dockerization
dockerfile
requirements.txt
app.py
🚀 Deployment Instructions
Building the Docker Image
Execute the following command in the project directory:​
docker build -t knikhil999/simpletimeservice .
Running the Docker Container
Run the container in detached mode and map port 5000:​
docker run -d -p 5000:5000 flask-ip-timestamp
🌐 Accessing the Application
Local Access
Navigate to http://localhost:5000 in your web browser.​

Remote Access (EC2)
Navigate to http://<EC2-Public-IP>:5000 in your web browser. Ensure that:​

The EC2 instance's security group allows inbound traffic on port 5000.

The application is running, and the Docker container is active.​

🧪 Testing the Application
Send a GET request to the root endpoint:​
curl http://localhost:5000
Edit
{
  "ip": "127.0.0.1",
  "timestamp": "2025-04-15T07:00:21.254951Z"
}

