/* Requires the Docker Pipeline plugin */
pipeline {
    agent any
    tools { 
        maven 'Maven 3.8.7' 
        jdk 'jdk17' 
    }
    stages {
        stage('Compile') {
            environment {
                  HOME="."
                }
            steps {
                sh './mvnw package -P css'
            }
        }
        stage('Test') { 
            environment {
                  HOME="."
                }
            steps {
                sh './mvnw test -P css'
            }
        }
        stage('Build Docker Image') { 
            environment {
                  HOME="."
                }
            steps {
                sh './mvnw spring-boot:build-image'
            }
        }
    }
}