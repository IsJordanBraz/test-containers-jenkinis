pipeline {
    agent any

    environment {
        TC_CLOUD_TOKEN = credentials('tc-cloud-token-secret-id')
    }

    stages {
        stage('TCC SetUp') {
            steps {
                sh "curl -fsSL https://get.testcontainers.cloud/bash | sh"
            }
        }
        stage('Test') {
            steps {
                ./mvnw test
            }
        }
    }
}