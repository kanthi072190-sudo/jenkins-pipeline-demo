pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo "Building the application..."
                // Example: sh 'mvn clean package'
            }
        }

        stage('Test') {
            steps {
                echo "Running unit tests..."
                // Example: sh 'mvn test'
            }
            post {
                success {
                    emailext (
                        to: 'kanthi072190@gmail.com',
                        subject: "Test Stage Success: ${env.JOB_NAME} #${env.BUILD_NUMBER}",
                        body: """<p><b>Project:</b> ${env.JOB_NAME}</p>
                                 <p><b>Stage:</b> Test</p>
                                 <p><b>Result:</b> SUCCESS</p>
                                 <p><a href="${env.BUILD_URL}console">Console log</a></p>""",
                        attachLog: true
                    )
                }
                failure {
                    emailext (
                        to: 'kanthi072190@gmail.com',
                        subject: "Test Stage Failed: ${env.JOB_NAME} #${env.BUILD_NUMBER}",
                        body: """<p><b>Project:</b> ${env.JOB_NAME}</p>
                                 <p><b>Stage:</b> Test</p>
                                 <p><b>Result:</b> FAILURE</p>
                                 <p><a href="${env.BUILD_URL}console">Console log</a></p>""",
                        attachLog: true
                    )
                }
            }
        }

        stage('Security Scan') {
            steps {
                echo "Running security scan..."
                // Example: sh 'mvn sonar:sonar'
            }
            post {
                success {
                    emailext (
                        to: 'kanthi072190@gmail.com',
                        subject: "Security Scan Success: ${env.JOB_NAME} #${env.BUILD_NUMBER}",
                        body: """<p><b>Project:</b> ${env.JOB_NAME}</p>
                                 <p><b>Stage:</b> Security Scan</p>
                                 <p><b>Result:</b> SUCCESS</p>
                                 <p><a href="${env.BUILD_URL}console">Console log</a></p>""",
                        attachLog: true
                    )
                }
                failure {
                    emailext (
                        to: 'kanthi072190@gmail.com ',
                        subject: "Security Scan Failed: ${env.JOB_NAME} #${env.BUILD_NUMBER}",
                        body: """<p><b>Project:</b> ${env.JOB_NAME}</p>
                                 <p><b>Stage:</b> Security Scan</p>
                                 <p><b>Result:</b> FAILURE</p>
                                 <p><a href="${env.BUILD_URL}console">Console log</a></p>""",
                        attachLog: true
                    )
                }
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploying application..."
                // Example: sh './deploy.sh'
            }
        }
    }
}
