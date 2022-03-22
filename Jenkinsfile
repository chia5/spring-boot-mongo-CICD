pipeline {
    agent { label 'prod' }
    
    stages{
        stage('Checkout') {
            steps{
                git branch: 'main', url: 'https://github.com/chia5/spring-boot-mongo-CICD.git'
            }
        }
        
        stage('Build') {
            steps{
            echo "Building Jar Componect ..."
            sh "mvn clean package"
            }
        }
    }
}
