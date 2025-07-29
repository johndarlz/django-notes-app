title: "🚀 Full-Stack Notes App with CI/CD Pipeline using Jenkins, Docker, and AWS"
note: "⚠️ Note: This project (simple notes app) was forked from another repository and is used purely for automating deployment and CI/CD processes using Jenkins and Docker."

tools_used:
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

project_overview: >
  This is a full-stack Notes App built using React for the frontend and Django for the backend.
  The application is containerized using Docker and deployed using Jenkins CI/CD on an AWS EC2 instance,
  with Nginx configured as a reverse proxy.
  This project also demonstrates the use of Jenkins agents, shared libraries, role-based access control,
  and DockerHub for container image hosting.

requirements:
  - Python 3.9+
  - Node.js
  - Docker
  - Docker Compose
  - Jenkins
  - AWS EC2 Instance
  - Nginx

installation_and_setup:
  steps:
    - step: Clone the Repository
      commands:
        - git clone https://github.com/LondheShubham153/django-notes-app.git
        - cd django-notes-app

    - step: Build the Docker Image
      commands:
        - docker build -t notes-app .

    - step: Run the Docker Container
      commands:
        - docker run -d -p 8000:8000 notes-app:latest

docker_compose:
  optional: true
  up_command: docker-compose up --build -d
  push_to_dockerhub:
    - docker tag notes-app:latest your-dockerhub-username/notes-app:latest
    - docker push your-dockerhub-username/notes-app:latest

nginx_setup:
  install:
    - sudo apt-get update
    - sudo apt install nginx
  config_file: /etc/nginx/sites-available/default
  configuration: |
    server {
        listen 80;
        server_name your-domain.com;

        location / {
            proxy_pass http://localhost:8000;
            proxy_set_header Host $host;
            proxy_set_header X-Real-IP $remote_addr;
        }
    }
  restart_command: sudo systemctl restart nginx

jenkins_pipeline:
  tasks:
    - Clone repository from GitHub
    - Build Docker image
    - Push image to DockerHub
    - Deploy container on EC2
    - Use Jenkins Shared Libraries for reusable code
    - Monitor process using Stage View Plugin

  agent_setup:
    - Launch EC2 instance on AWS
    - Install Java and Jenkins agent
    - Connect to Jenkins master
    - Assign node labels and manage jobs accordingly

jenkins_role_based_access_control:
  - Created custom Jenkins users
  - Assigned roles using Role-Based Strategy Plugin
  - Restricted access based on permissions

learnings:
  - End-to-end CI/CD pipeline setup using Jenkins
  - Dockerizing and deploying full-stack applications
  - Using DockerHub for storing images
  - Reusability with Jenkins Shared Libraries
  - Managing Jenkins agents (nodes) on AWS
  - Reverse proxy setup with Nginx
  - User role and permission management in Jenkins

license: MIT License

acknowledgements:
  - Original forked repo: LondheShubham153/django-notes-app
  - Community for Jenkins & DevOps knowledge sharing
