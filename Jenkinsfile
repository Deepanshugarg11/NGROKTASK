pipeline {
    agent any

    environment {
        DOCKER_IMAGE = 'react-app'
        DOCKER_CONTAINER = 'react-container'
        STAGING_SERVER = 'staging.example.com'
        PRODUCTION_SERVER = 'production.example.com'
        EMAIL_RECIPIENT = 'deepanshu4773.be23@chitkara.edu.in'
    }

    stages {
        stage('Build') {
            steps {
                echo 'Building the React application...'
                echo 'Tools: Yarn, Parcel, Rollup'
                echo 'Integration Steps: Install dependencies using Yarn, bundle the React app with Parcel or Rollup, and generate optimized production assets.'
                echo 'What it does: Compiles React code into a minified, production-ready format'
            }
        }

        stage('Unit and Integration Tests') {
            steps {
                echo 'Running unit and integration tests...'
                echo 'Tools: AVA, Karma, Chai'
                echo 'Integration Steps: Use AVA or Karma for unit testing, Chai for assertions, and ensure test coverage meets project standards.'
                echo 'What it does: Tests individual React components and their integration with state and API'
            }
        }

        stage('Code Analysis') {
            steps {
                echo 'Performing static code analysis with ESLint and Codacy...'
                echo 'Tools: Codacy, Sonarlint, TSLint'
                echo 'Integration Steps: Run Codacy for automated code reviews and Sonarlint for local static analysis.'
                echo 'What it does: Ensures the code follows best practices and detects potential bugs.'
            }
        }

        stage('Security Scan') {
            steps {
                echo 'Running security scan with Trivy...'
                echo 'Tools: Trivy, WhiteSource, Bandit'
                echo 'Integration Steps: Use Trivy for scanning container vulnerabilities and Bandit for detecting security issues in Python scripts (if applicable).'
                echo 'What it does: Identifies security risks in project dependencies.'
            }
        }

        stage('Deploy to Staging') {
            steps {
                echo 'Deploying React app to staging using Docker...'
                echo 'Tools: Podman, Traefik, Apache HTTP Server'
                echo 'Integration Steps: Build a container with Podman, use Traefik as a reverse proxy, and serve the app with Apache.'
                echo 'What it does: Deploys the React app inside a container, making it accessible for testing.'
            }
        }

        stage('Integration Tests on Staging') {
            steps {
                echo 'Running end-to-end tests on staging with TestCafe...'
                echo 'Tools: TestCafe, Nightwatch.js, Robot Framework'
                echo 'Integration Steps: Execute TestCafe test cases against the staging URL and validate workflows with Nightwatch.js.'
                echo 'What it does: Ensures that the deployed React app works correctly in the staging environment.'
            }
        }

        stage('Deploy to Production') {
            steps {
                echo 'Deploying React app to production using Docker...'
                echo 'Tools: Azure App Service, DigitalOcean App Platform, Google Cloud Run'
                echo 'Integration Steps: Deploy the Docker container to Azure App Service, DigitalOcean App Platform, or Google Cloud Run.'
                echo 'What it does: Deploys the React app in a production-ready container environment.'
            }
        }
    }

    post {
        success {
            echo 'Pipeline executed successfully!'
            echo 'Tools: Microsoft Teams Webhook, Webhooks, Datadog'
            echo 'Integration Steps: Notify the team using Microsoft Teams Webhook and monitor performance with Datadog.'
            echo 'What it does: Confirms the React app is built, tested, analyzed, scanned, and deployed correctly.'

            mail subject: "Jenkins Pipeline Success: React App",
                      body: "The Jenkins pipeline has completed successfully.\n\nBuild Details:\n- Job Name: ${JOB_NAME}\n- Build Number: ${BUILD_NUMBER}\n- Status: SUCCESS\n- Logs: ${BUILD_URL}\n\nRegards,\nJenkins",
                      to: "${EMAIL_RECIPIENT}"
        }
        
        failure {
            echo 'Pipeline failed! Check the logs for more details.'
            echo 'Tools: Loki, Splunk, New Relic'
            echo 'Integration Steps: Capture logs using Loki, analyze them with Splunk, and monitor performance with New Relic.'
            echo 'What it does: Notifies the team of pipeline failures for immediate attention.'

            mail subject: "Jenkins Pipeline Failure: React App",
                      body: "The Jenkins pipeline has failed.\n\nBuild Details:\n- Job Name: ${JOB_NAME}\n- Build Number: ${BUILD_NUMBER}\n- Status: FAILURE\n- Logs: ${BUILD_URL}\n\nPlease check the logs and take necessary actions.\n\nRegards,\nJenkins",
                      to: "${EMAIL_RECIPIENT}"
        }
    }
}
