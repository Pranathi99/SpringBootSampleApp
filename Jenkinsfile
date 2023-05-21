pipeline {
    agent any
    stages {
        stage('git repo clone') {
            steps {
                git branch: 'main', url: 'https://github.com/Pranathi99/SpringBootSampleApp.git'
            }
        }
        stage('clean') {
            steps {
                sh "mvn clean"
            }
        }
        stage('package') {
            steps {
                sh "mvn package"
            }
        }
         stage('docker build') {
             steps {
                 sh "docker build -t spring-application ."
             }
         }
        stage('docker run') {
             steps {
                 sh "docker run -p 80:8080 --name spring spring-application:latest"
             }
        }
    }
}
