pipeline {
    agent any
    environment {
        GIT_REPO = 'https://github.com/djmcr18/jenkins-ci-pipeline.git'
        STAGING_SERVER = 'staging-server-address'
        PRODUCTION_SERVER = 'production-server-address'
    }
    stages {
        stage('Build') {
            steps {
                echo "Building the code using Maven"
                // Actual command if needed: sh 'mvn clean install'
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo "Running unit tests with JUnit and integration tests with Selenium"
                // Notify after tests
                mail to: 'djmcr.18@gmail.com',
                    subject: "Tests Completed: ${env.JOB_NAME} #${env.BUILD_NUMBER}",
                    body: "The Unit and Integration Tests stage has completed for ${env.JOB_NAME} #${env.BUILD_NUMBER}.",
                    attachLog: true
            }
        }
        stage('Code Analysis') {
            steps {
                echo "Analyzing the code with SonarQube"
                // Example: sh 'sonar-scanner'
            }
        }
        stage('Security Scan') {
            steps {
                echo "Performing security scan with OWASP Dependency-Check"
                // Notify after security scan
                mail to: 'djmcr.18@gmail.com',
                    subject: "Security Scan Completed: ${env.JOB_NAME} #${env.BUILD_NUMBER}",
                    body: "The Security Scan stage has completed for ${env.JOB_NAME} #${env.BUILD_NUMBER}.",
                    attachLog: true
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo "Deploying to staging on AWS EC2"
                // Example deployment command
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo "Running integration tests on staging environment with Selenium"
                // Example: sh 'mvn verify -Dselenium.staging'
            }
        }
        stage('Deploy to Production') {
            steps {
                echo "Deploying to production on AWS EC2"
                // Example deployment command
            }
        }
    }
    post {
        always {
            echo "Pipeline completed."
        }
        success {
            mail to: 'djmcr.18@gmail.com',  // Update the recipient email address
                 subject: "Pipeline Success: ${env.JOB_NAME} #${env.BUILD_NUMBER}",
                 body: "The pipeline ${env.JOB_NAME} #${env.BUILD_NUMBER} completed successfully.\n\nCheck Jenkins for details."
        }
        failure {
            mail to: 'djmcr.18@gmail.com',  // Update the recipient email address
                 subject: "Pipeline Failure: ${env.JOB_NAME} #${env.BUILD_NUMBER}",
                 body: "The pipeline ${env.JOB_NAME} #${env.BUILD_NUMBER} failed.\n\nCheck Jenkins for details."
        }
    }
}
