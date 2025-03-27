pipeline {
    agent any

    environment {
        EMAIL_RECIPIENT = 'deepanshu@gmail.com'
        USER_EMAIL = 'dipanshugarg13@gmail.com'
        AWS_CREDENTIALS = credentials('aws-credentials')
    }

    stages {
        // Stage 1: Build
        stage('Build') {
            steps {
                echo 'Building the application using Maven, Gradle, or Ant...'
            }
        }

        // Stage 2: Unit and Integration Tests
        stage('Unit and Integration Tests') {
            steps {
                echo 'Running unit tests with JUnit, TestNG, or NUnit...'
                echo 'Running integration tests with Selenium, Cucumber, or Postman...'
            }
        }

        // Stage 3: Code Analysis
        stage('Code Analysis') {
            steps {
                echo 'Analyzing code using SonarQube, Checkstyle, or PMD...'
            }
        }

        // Stage 4: Security Scan
        stage('Security Scan') {
            steps {
                echo 'Performing security scan with OWASP Dependency Check, Snyk, or Veracode...'
            }
        }

        // Stage 5: Deploy to Staging
        stage('Deploy to Staging') {
            steps {
                echo 'Deploying to AWS EC2 using Ansible, Terraform, or Kubernetes...'
            }
        }

        // Stage 6: Integration Tests on Staging
        stage('Integration Tests on Staging') {
            steps {
                echo 'Running Selenium integration tests on Staging with Selenium, Cypress, or Playwright...'
            }
        }

        // Stage 7: Deploy to Production
        stage('Deploy to Production') {
            steps {
                echo 'Deploying to AWS EC2 Production server using Jenkins, Docker, or Helm...'
            }
        }
    }

    post {
        success {
            echo 'Pipeline executed successfully!'
            mail to: "${USER_EMAIL}",
                 subject: "Pipeline Execution Successful",
                 body: "The entire pipeline has completed successfully."
        }
        failure {
            echo 'Pipeline failed! Check the logs for more details.'
            mail to: "${USER_EMAIL}",
                 subject: "Pipeline Execution Failed",
                 body: "The pipeline has failed. Please check the Jenkins logs for more details."
        }
    }
}
