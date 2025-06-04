pipeline {
    agent any

    tools {
        gradle 'Gradle 4.4.1'   // Match this with Global Tool Configuration
        jdk 'JDK 11'            // Match this with your configured JDK name
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/harshe22/gradlePipeline.git'
            }
        }

        stage('Verify Gradle Version') {
            steps {
                sh 'gradle --version'
            }
        }

        stage('Build') {
            steps {
                sh 'gradle build'
            }
        }

        stage('Test') {
            steps {
                sh 'gradle test'
            }
        }

        stage('Run Application') {
            steps {
                sh 'gradle run'
            }
        }
    }

    post {
        success {
            echo '✅ Build and deployment successful!'
        }
        failure {
            echo '❌ Build failed!'
        }
    }
}
