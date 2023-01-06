/* Requires the Docker Pipeline plugin */
pipeline {
    agent { docker { image 'maven:3.8.7-eclipse-temurin-11' } }
    stages {
        stage('Compile') {
            steps {
                sh './mvnw package -P css'
            }
        }
        stage('Test') { 
            steps {
                sh './mvnw test -P css'
            }
        }
        stage('BuildDocker') { 
            steps {
                /* sh './mvnw spring-boot:build-image' */
            }
        }
    }
}