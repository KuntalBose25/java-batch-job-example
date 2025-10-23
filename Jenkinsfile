pipeline {
    agent any
    options {
        skipStagesAfterUnstable()
    }
    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/KuntalBose25/java-batch-job-example.git'
            }
        }
        stage('Build') {
            steps {
                bat 'mvn clean install'
            }
        }
        stage('Test') {
            steps {
                bat 'mvn test'
                junit 'target/surefire-reports/*.xml'
            }
        }
    }
            post {
                always {
                    junit 'target/surefire-reports/*.xml'
                }
            }
        }
