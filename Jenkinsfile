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
        
        stage('Build Image') {
            steps{
                script {
                    docker.withRegistry('https://registry.hub.docker.com', 'dockerhub') {
                    /*Build Docker Image locally*/
                    myImage = docker.build("chash07/springboot-mongodb:latest ")

                    /*Push the container to the Registry */
                    myImage.push()
                    }
                }
            }
        }
    }
}
