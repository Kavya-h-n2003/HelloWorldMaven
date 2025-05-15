pipeline {
    agent any

    tools {
        maven 'maven' // Ensure this matches the Maven installation name in Jenkins
    }

    environment {
        JAR_NAME = 'HelloWorldMaven-0.0.1-SNAPSHOT.jar'
    }

    stages {
        stage('Checkout') {
            steps {
                echo 'Checking out source code...'
                git branch: 'main', url: 'https://github.com/Kavya-h-n2003/HelloWorldMaven.git'
            }
        }

        stage('Build') {
            steps {
                echo 'Building project using Maven...'
                bat 'mvn clean package'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                bat 'mvn test'
            }
        }

        stage('Run Application') {
            steps {
                echo 'Running the application...'
                bat 'dir target' // View files in target folder (for debugging)
                bat "java -jar target\\%JAR_NAME%"
            }
        }
    }

    post {
        failure {
            echo 'Pipeline failed. Check the logs for errors.'
        }
        success {
            echo 'Pipeline completed successfully!'
        }
    }
}
