pipeline{
    agent any
        tools{
            jdk 'java'
            maven 'maven'
        }
    
    stages{
        stage('Chekout'){
            steps{
                git branch :'main',url:'https://github.com/Kavya-h-n2003/HelloWorldMaven.git'
                }
            }
        stage('Build'){
            steps{
                bat 'mvn clean package'
                }
            }
        stage('Test'){
            steps{
                bat 'mvn test'
                }
            }
        stage('Run Application'){
            steps{
                bat 'java -jar target/HelloMaven-0.0.1-SNAPSHOT.jar'
                }
            }
        
    }
}
