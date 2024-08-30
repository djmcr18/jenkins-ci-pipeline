{\rtf1\ansi\ansicpg1252\cocoartf2709
\cocoatextscaling0\cocoaplatform0{\fonttbl\f0\fswiss\fcharset0 Helvetica;}
{\colortbl;\red255\green255\blue255;}
{\*\expandedcolortbl;;}
\paperw11900\paperh16840\margl1440\margr1440\vieww11520\viewh19620\viewkind0
\pard\tx720\tx1440\tx2160\tx2880\tx3600\tx4320\tx5040\tx5760\tx6480\tx7200\tx7920\tx8640\pardirnatural\partightenfactor0

\f0\fs24 \cf0 pipeline \{\
    agent any\
    environment \{\
        GIT_REPO = 'https://github.com/djmcr18/jenkins-ci-pipeline.git'\
        STAGING_SERVER = 'staging-server-address' // Replace with actual staging server address\
        PRODUCTION_SERVER = 'production-server-address' // Replace with actual production server address\
    \}\
    stages \{\
        stage('Build') \{\
            steps \{\
                echo "Building the code using Maven"\
                // Actual command if needed: sh 'mvn clean install'\
            \}\
        \}\
        stage('Unit and Integration Tests') \{\
            steps \{\
                echo "Running unit tests with JUnit and integration tests with Selenium"\
                // Actual command if needed: sh 'mvn test'\
            \}\
        \}\
        stage('Code Analysis') \{\
            steps \{\
                echo "Analyzing the code with SonarQube"\
                // Example: sh 'sonar-scanner'\
            \}\
        \}\
        stage('Security Scan') \{\
            steps \{\
                echo "Performing security scan with OWASP Dependency-Check"\
                // Example: sh 'dependency-check --scan /path/to/project'\
            \}\
        \}\
        stage('Deploy to Staging') \{\
            steps \{\
                echo "Deploying to staging on AWS EC2"\
                // Example deployment command\
            \}\
        \}\
        stage('Integration Tests on Staging') \{\
            steps \{\
                echo "Running integration tests on staging environment with Selenium"\
                // Example: sh 'mvn verify -Dselenium.staging'\
            \}\
        \}\
        stage('Deploy to Production') \{\
            steps \{\
                echo "Deploying to production on AWS EC2"\
                // Example deployment command\
            \}\
        \}\
    \}\
    post \{\
        always \{\
            echo "Pipeline completed."\
        \}\
        success \{\
            mail to: \'92s223341726@deakin.edu.au',\
                 subject: "Pipeline Success: $\{env.JOB_NAME\} #$\{env.BUILD_NUMBER\}",\
                 body: "The pipeline $\{env.JOB_NAME\} #$\{env.BUILD_NUMBER\} completed successfully.",\
                 attachLog: true\
        \}\
        failure \{\
            mail to: \'92s\'92223341726@deakin.edu.au,\
                 subject: "Pipeline Failure: $\{env.JOB_NAME\} #$\{env.BUILD_NUMBER\}",\
                 body: "The pipeline $\{env.JOB_NAME\} #$\{env.BUILD_NUMBER\} failed.",\
                 attachLog: true\
        \}\
    \}\
\}\
}