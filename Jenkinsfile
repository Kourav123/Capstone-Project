pipeline {
    agent any
     tools {
        maven "MAVEN"
    }

    stages {
        stage("version of software"){
            steps{
                sh "java --version"
                sh "mvn --version"
                sh "docker --version"
                sh "docker-compose --version"
            }
        }
        stage("Build Docker Image"){
            steps{
               // sh "mvn clean"
                //sh "mvn package"
               // Build Docker image
               // sh "docker build -t angular-spring-boot:v1 ."
                 sh "docker build -t mypet-spring-boot:v1 ."
            }
        }
        stage("run the docker containers"){
            steps{
                sh "docker-compose down"
                sh "docker-compose up --build -d"       
            }
        }
        stage("Check images and running containers"){
            steps{
                sh "docker images"
                sh "docker ps"       
            }
        }
    }
}
