pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building Docker Image..'
		chmod +X mvnw
		./mvnw spring-boot:build-image
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
