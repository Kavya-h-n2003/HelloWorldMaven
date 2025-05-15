pipeline {
    agent any
    tools {
        maven 'maven' // Make sure the name matches the Maven installation in Jenkins
    }
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Kavya-h-n2003/HelloWorldMaven.git'
            }
        }
        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
        stage('Run Application') {
            steps {
                sh 'java -jar target/HelloMaven-0.0.1-SNAPSHOT.jar'
            }
        }
    }
}