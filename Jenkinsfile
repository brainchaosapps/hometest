/* Requires the Docker Pipeline plugin */
pipeline {
    agent {
        docker {
            image 'maven:3.8.7-eclipse-temurin-11' 
        }
    }
    options {
        skipStagesAfterUnstable()
    }
    stages {
        stage('Compile') {
            steps {
                /* sh './mvnw package' */ 
                sh 'echo 1'
            }
        }
        stage('Test') { 
            steps {
                /* sh './mvnw test' */
                sh 'echo 2'
            }
        }
        stage('Build Docker Image') { 
            steps {
                sh './mvnw spring-boot:build-image'
            }
        }
    }
}
