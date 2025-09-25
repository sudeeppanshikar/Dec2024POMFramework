pipeline {
    agent any

    tools {
        maven 'maven'
        jdk 'jdk'
    }

    stages {
        stage('Clean Workspace') {
            steps {
                cleanWs()
            }
        }

        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/sudeeppanshikar/Dec2024POMFramework.git'
            }
        }

        stage('Build') {
            steps {
                echo "Building the project"
                sh 'mvn clean compile'
            }
        }

        stage('Run Unit & Integration Tests') {
            steps {
                echo "Running tests"
                // Ignore test failures so Allure can generate results
                sh 'mvn test -Dmaven.test.failure.ignore=true'
            }
        }

        stage('Publish Allure Reports') {
            steps {
                script {
                    allure([
                        includeProperties: false,
                        reportBuildPolicy: 'ALWAYS',
                        results: [[path: 'allure-results']]
                    ])
                }
            }
        }

        stage('Deploy to Dev') {
            steps {
                echo "Deploying to Dev"
            }
        }
    }

    post {
        always {
            // Publish test results for this run only
            junit allowEmptyResults: true, testResults: 'target/surefire-reports/*.xml'
        }
    }
}
