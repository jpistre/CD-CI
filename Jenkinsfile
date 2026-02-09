pipeline {
    agent any
    tools {
        maven 'mvn'
    }

    stages {
        stage('Checkout') {
          steps {
            git url: 'https://github.com/jpistre/CD-CI.git', branch: 'main'
          }
        }
        stage('Build PetClinic JAR') {
            steps {
                sh 'mvn clean install -DskipTests'
            }
        }
        stage('Build Docker Image') {
            steps {
                sh 'docker compose build'
            }
        }
    }
}
