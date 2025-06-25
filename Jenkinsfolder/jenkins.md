# 🚀 Jenkins CI/CD Overview

## 🧰 What is Jenkins?

[Jenkins](https://www.jenkins.io/) is an open-source automation server that helps automate the **building**, **testing**, and **deployment** of software. It’s highly extensible with plugins and integrates with many DevOps tools.

---

## ⚙️ How Jenkins Works

1. **Install Jenkins**
   - Download from [jenkins.io](https://www.jenkins.io/download/)
   - Start it locally:
     ```bash
     java -jar jenkins.war
     ```

2. **Configure a Job**
   - Create a new **Job** (Freestyle or Pipeline)
   - Add **build triggers** (like Git push, cron)
   - Define **build steps** (Shell scripts, Maven, etc.)

3. **Build & Deploy**
   - Triggers can be automatic or manual
   - View pipeline stages and results
   - Artifacts can be stored or deployed

---

## 📄 Example Jenkinsfile

```groovy
pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building...'
                sh './gradlew build'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing...'
                sh './gradlew test'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying...'
            }
        }
    }
}

