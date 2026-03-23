# 🚀 Express Backend API with CI/CD (Jenkins)

This project demonstrates a simple Express.js backend API with a complete CI/CD pipeline using Jenkins, GitHub, AWS EC2, and PM2.

---

## 📌 Project Overview

* Developed a REST API using Express.js
* Implemented GET and POST APIs
* Automated deployment using Jenkins
* Integrated GitHub for version control
* Used PM2 to manage and run the application

---

## 🛠️ Tech Stack

* Node.js (Express)
* Jenkins
* GitHub
* AWS EC2
* PM2

---

## 📂 Project Structure

```
backend-express/
│
├── server.js
├── package.json
└── package-lock.json
```

---

## ⚙️ Setup & Installation

### 1. Clone Repository

```bash
git clone https://github.com/Tanuja-74/FLASK-APP-CI-CD.git
cd FLASK-APP-CI-CD/backend-express
```

---

### 2. Install Dependencies

```bash
npm install
```

---

### 3. Run Application

```bash
node server.js
```

---

### 4. Access API

```
http://<YOUR-EC2-PUBLIC-IP>:3000/users
```

---

## 📡 API Endpoints

### 🔹 GET Users

```
GET /users
```

Response:

```json
[]
```

---

### 🔹 POST User

```
POST /users
```

Body:

```json
{
  "name": "Tanuja",
  "email": "tanuja@gmail.com",
  "contact": "1234567890"
}
```

Response:

```json
{
  "message": "User saved successfully",
  "data": {
    "id": 1,
    "name": "Tanuja",
    "email": "tanuja@gmail.com",
    "contact": "1234567890"
  }
}
```

---

## 🔄 CI/CD Pipeline (Jenkins)

### Pipeline Stages:

1. Install Dependencies
2. Run Application using PM2

---

## 📜 Jenkinsfile

```groovy
pipeline {
    agent any

    stages {

        stage('Install Dependencies') {
            steps {
                dir('backend-express') {
                    sh 'npm install'
                }
            }
        }

        stage('Run App') {
            steps {
                dir('backend-express') {
                    sh '/usr/bin/pm2 restart express-app || /usr/bin/pm2 start server.js --name express-app'
                }
            }
        }
    }
}
```

---

## 🔔 Webhook Integration

GitHub webhook triggers Jenkins pipeline automatically on every code push.

```
http://<YOUR-EC2-PUBLIC-IP>:8080/github-webhook/
```

---

## 📊 Output

* Jenkins pipeline runs successfully
* Express backend deployed automatically
* API runs continuously using PM2

---

## 📸 Screenshots

(Add screenshots)

* Jenkins Build Success
* API response in browser/Postman

---

## 💡 Key Learnings

* Building REST APIs using Express.js
* CI/CD pipeline implementation
* Jenkins automation
* GitHub integration
* Process management using PM2

---

## 👩‍💻 Author

**Tanuja Kurane**

---

## ⭐ Future Enhancements

* Add database integration (MongoDB/MySQL)
* Add authentication (JWT)
* Dockerize the application
* Deploy using Kubernetes

---
