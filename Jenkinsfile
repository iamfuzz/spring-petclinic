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
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
		sh 'VERSION=`ls target/*.jar |sed -e "s/\.jar//g"|sed -e "s/spring-petclinic-//g"|xargs basename` && docker tag spring-petclinic:$VERSION iamfuzz.jfrog.io/docker/spring-petclinic:$VERSION && docker push iamfuzz.jfrog.io/docker/spring-petclinic:$VERSION'
            }
        }
    }
}
