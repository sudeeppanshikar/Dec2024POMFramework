pipeline {
    agent any

    tools {
        maven 'maven'
        jdk 'jdk'
    }

    stages {
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
            script {
                // Mark build as unstable if tests failed
                def testFailed = sh(script: 'grep -q "Failures:" target/surefire-reports/*.txt', returnStatus: true)
                if (testFailed == 0) {
                    currentBuild.result = 'UNSTABLE'
                    echo "Some tests failed — build marked UNSTABLE"
                } else {
                    echo "All tests passed"
                }
            }
        }
    }
}
