# 🚀 Razorpay DevOps Project-1

## 📌 Introduction

This project demonstrates a production-style CI/CD pipeline for a Dockerized web application deployed on AWS EC2.

The objective of this project is to:

- Containerize a web application using Docker
- Automate image building using GitHub Actions
- Push images to Docker Hub
- Deploy automatically to an AWS EC2 instance
- Implement secure SSH-based deployment
- Replace containers automatically on every push

This simulates a real-world DevOps workflow used in modern engineering teams.
=======================================================================================
---

## 🐳 Step 1: Local Docker Build & Testing

Before implementing CI/CD, the application was first containerized and tested locally.

### 🔹 Dockerfile Used

```dockerfile
FROM nginx:alpine
COPY app/ /usr/share/nginx/html
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
---------------------------------------------------------------------------------------

🔹 Build Docker Image
docker build -t razorpay-devops-project-1:v1 .

🔹 Run Container Locally
docker run -d -p 8080:80 razorpay-devops-project-1:v1


The application was successfully accessible at:

http://localhost:8080

📸 Local Docker Build Output

---------------------------------------------------------------------------------------


## 🐳 Step 2: Docker Hub Integration

After validating the application locally, the Docker image was pushed to Docker Hub for remote access and cloud deployment.

---

### 🔹 Login to Docker Hub

```bash
docker login
---------------------------------------------------------------------------------------
🔹 Tag Docker Image
docker tag razorpay-devops-project-1:v1 chetan70/razorpay-devops-project-1:v1

🔹 Push Image to Docker Hub
docker push chetan70/razorpay-devops-project-1:v1


Image was successfully pushed to:

docker.io/chetan70/razorpay-devops-project-1

📸 Docker Push Output

📸 Docker Hub Repository

✅ Outcome

Image successfully versioned

Public registry configured

Ready for cloud-based deployment
---------------------------------------------------------------------------------------