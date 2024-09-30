pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                echo 'Building...'
            }
        }
        
        stage('Unit and Integration Tests') {
            steps {
                echo 'Running Unit and Integration Tests...'
                // Test commands here
            }
            post {
                success {
                    emailext(
                        subject: "Jenkins: Tests Passed",
                        body: "The Unit and Integration Tests have passed.",
                        recipientProviders: [[$class: 'krishnahkhengar007@gmail.com']],
                        attachLog: true
                    )
                }
                failure {
                    emailext(
                        subject: "Jenkins: Tests Failed",
                        body: "The Unit and Integration Tests have failed.",
                        recipientProviders: [[$class: 'krishnahkhengar007@gmail.com']],
                        attachLog: true
                    )
                }
            }
        }
        
        stage('Code Analysis') {
            steps {
                echo 'Running Code Analysis...'
            }
        }
        
        stage('Security Scan') {
            steps {
                echo 'Performing Security Scan...'
            }
            post {
                success {
                    emailext(
                        subject: "Jenkins: Security Scan Passed",
                        body: "The security scan has passed with no vulnerabilities found.",
                        recipientProviders: [[$class: 'krishnahkhengar007@gmail.com']],
                        attachLog: true
                    )
                }
                failure {
                    emailext(
                        subject: "Jenkins: Security Scan Failed",
                        body: "The security scan has failed. Please review the logs for vulnerabilities.",
                        recipientProviders: [[$class: 'krishnahkhengar007@gmail.com']],
                        attachLog: true
                    )
                }
            }
        }
        
        stage('Deploy to Staging') {
            steps {
                echo 'Deploying to Staging...'
            }
        }
        
        stage('Integration Tests on Staging') {
            steps {
                echo 'Running Integration Tests on Staging...'
            }
        }
        
        stage('Deploy to Production') {
            steps {
                echo 'Deploying to Production...'
            }
        }
    }
    
    post {
        always {
            echo 'Pipeline Completed.'
        }
    }
}
