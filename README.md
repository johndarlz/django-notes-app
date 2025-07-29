# 📝 Simple Notes App with CI/CD using Jenkins, Docker & AWS

> ⚠️ *Note: This project (Simple Notes App) was forked from another repository and is used purely for automating deployment and CI/CD processes using Jenkins and Docker.*

---

## 🚀 Project Overview

- ✅ Full-stack Notes App (`React + Django`)
- ✅ Forked from open-source repo
- ✅ Automated pipeline using Jenkins on AWS EC2
- ✅ Dockerized backend and frontend
- ✅ Deployment to server via Jenkins agent
- ✅ Reverse proxy with Nginx
- ✅ Docker image pushed to DockerHub

---

## 🔧 Tools Used

- React  
- Django  
- Docker  
- Docker Compose  
- Jenkins  
- AWS EC2  
- Nginx  
- GitHub  
- Jenkins Shared Libraries  
- Jenkins Stage View Plugin  

---

## ⚙️ How It Works

The project is a full-stack Notes App using React for the frontend and Django for the backend. It is forked from [LondheShubham153/django-notes-app](https://github.com/LondheShubham153/django-notes-app) and used to automate deployment with Jenkins and Docker on an AWS EC2 instance.

The application is containerized using Docker. Jenkins pulls the latest code from GitHub, builds the Docker image, pushes it to DockerHub, and deploys it to the AWS EC2 instance using Jenkins agents. Docker Compose can optionally be used for managing multi-container services. Nginx is configured as a reverse proxy to expose the app on port 80.

Jenkins Shared Libraries are used for reusing functions across stages, and the Stage View Plugin allows tracking the pipeline visually. Role-based access is enforced in Jenkins for security.

---
## 🧪 Jenkins CI/CD Pipeline

- Jenkins pulls code from GitHub on every commit to the `main` branch  
- Builds Docker image and tags it  
- Pushes the image to DockerHub  
- Jenkins agent (on AWS EC2) pulls and runs the container  
- Shared libraries are used to reuse logic  
- Stage View Plugin displays all pipeline stages clearly  

---

## 🔐 Jenkins Access Control

- Created multiple users in Jenkins  
- Used **Role-Based Strategy Plugin** to assign access  
- Limited job and view access per role  

---

## 📚 Learnings

- CI/CD automation using Jenkins  
- Dockerizing **React + Django** full-stack apps  
- Reusable pipeline steps via Shared Libraries  
- Jenkins node setup on **AWS EC2**  
- Nginx reverse proxy setup for container exposure  
- GitHub → DockerHub → EC2 pipeline flow  
- Jenkins access control and security handling  

---



## 🙋‍♂️ Author

**Kandukuri Jnaneswar (johndarlz)**  
📧 Email: [johnu.kandukuri@gmail.com](mailto:johnu.kandukuri@gmail.com)  
🔗 GitHub: [@johndarlz](https://github.com/johndarlz)  
