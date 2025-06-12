🚀 Flask + MySQL App — Dockerized & Kubernetes Ready
This is a full-stack two-tier web application built with Flask and MySQL, showcasing both Docker-based and Kubernetes-based deployments. Users can submit messages via a frontend, which are stored in a MySQL database and displayed on the page.

📌 Features
🐳 Docker + Docker Compose setup

☸️ Kubernetes deployment with Services, Deployments, PVC

⚙️ Flask-based backend with MySQL persistence

🧪 SQL insertion via API

🧼 Clean structure with .env support

Project Structure
your-repo-name/
├── app.py
├── Dockerfile
├── requirements.txt
├── docker-compose.yml
├── .env
├── k8s/
│   ├── mysql-deployment.yaml
│   ├── flask-deployment.yaml
│   ├── mysql-pv.yaml
│   ├── flask-service.yaml
│   └── mysql-service.yaml
└── templates/
    └── index.html
🚀 Getting Started with Docker Compose

Clone the Repository
git clone https://github.com/your-username/your-repo-name.git
cd your-repo-name
Add Environment Variables
Create a .env file:
touch .env
MYSQL_HOST=mysql
MYSQL_USER=root
MYSQL_PASSWORD=admin
MYSQL_DB=mydb

Run with Docker Compose
docker-compose up --build

Create the messages table in MySQL (use CLI, GUI, or PHPMyAdmin):
CREATE TABLE messages (
    id INT AUTO_INCREMENT PRIMARY KEY,
    message TEXT
);


☸️ Running on Kubernetes

🧱 Step 1: Setup Minikube or a Cluster
   Start Minikube:
   minikube start

🧰 Step 2: Apply Kubernetes Resources
kubectl apply -f k8s/mysql-pv.yaml
kubectl apply -f k8s/mysql-deployment.yaml
kubectl apply -f k8s/mysql-service.yaml

kubectl apply -f k8s/flask-deployment.yaml
kubectl apply -f k8s/flask-service.yaml
Wait for pods to be ready:
kubectl get pods

Step 3: Access the App
kubectl port-forward svc/flask-service 5000:5000

🧪 Test the App

🔁 Cleaning Up
Docker
 docker-compose down
Kubernetes
 kubectl delete -f k8s/


