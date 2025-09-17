pipeline {
    agent any
    stages {
        stage('Build') {
            steps { echo 'Building the code using Maven...' }
        }
        stage('Unit Tests') {
            steps { echo 'Running unit tests...' }
        }
        stage('Integration Tests') {
            steps { echo 'Running integration tests...' }
        }
        stage('Code Analysis') {
            steps { echo 'Checking code quality using SonarLint...' }
        }
        stage('Security Scan') {
            steps { echo 'Performing security scan using npm audit...' }
        }
        stage('Deploy to Staging') {
            steps { echo 'Deploying to staging environment...' }
        }
        stage('Deploy to Production') {
            steps { echo 'Deploying to production environment...' }
        }
    }
    post {
        always { echo 'Pipeline finished.' }
    }
}
