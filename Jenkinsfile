pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
		chmod +X mvnw
		./mvnw spring-boot:build-image
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
