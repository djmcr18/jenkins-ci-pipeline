pipeline {
    agent any
    environment {
        GIT_REPO = 'https://github.com/djmcr18/jenkins-ci-pipeline.git' // Replace with your GitHub repo
        STAGING_SERVER = 'staging-server-address' // Replace with actual staging server address
        PRODUCTION_SERVER = 'production-server-address' // Replace with actual production server address
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
                // Actual command if needed: sh 'mvn test'
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
                // Example: sh 'dependency-check --scan /path/to/project'
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
            mail to: 's223341726@deakin.edu.au',
                 subject: "Pipeline Success: ${env.JOB_NAME} #${env.BUILD_NUMBER}",
                 body: "The pipeline ${env.JOB_NAME} #${env.BUILD_NUMBER} completed successfully.",
                 attachLog: true
        }
        failure {
            mail to: 's223341726@deakin.edu.au',
                 subject: "Pipeline Failure: ${env.JOB_NAME} #${env.BUILD_NUMBER}",
                 body: "The pipeline ${env.JOB_NAME} #${env.BUILD_NUMBER} failed.",
                 attachLog: true
        }
    }
}
