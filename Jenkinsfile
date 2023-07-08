pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
		sh 'chmod +X mvnw'
		sh './mvnw spring-boot:build-image'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
		snykSecurity(
          		snykInstallation: 'iamfuzz',
          		snykTokenId: 'iamfuzz-token',
        		)
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
		sh 'chmod +X jf'
		sh './jf'
            }
        }
    }
}
