pipeline {
    agent any
    stages {
        stage('Download') {
            steps {
                echo "Download Code from Github"
                git branch: 'main', url: 'https://github.com/piyush-ptl/maven-jenkins10.git'
            }
        }
        stage('Build Docker Image') {
            steps {
                echo "Build the application docker image and push to Docker Hub"
                sh '''docker build -t piyushpatel21/java-webapp:v${BUILD_NUMBER} .
                docker tag piyushpatel21/java-webapp:v${BUILD_NUMBER} piyushpatel21/java-webapp:latest
                docker push piyushpatel21/java-webapp:v${BUILD_NUMBER}
                docker push piyushpatel21/java-webapp:latest
                '''
            }
        }
    }
}
