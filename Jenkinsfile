pipeline {
    agent any

    tools {
        nodejs 'NodeJS-20'
    }

    stages {

        stage('Clone Code') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/GauthamSanthsoh/devops.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                dir('welcome-react') {
                    sh 'npm install'
                }
            }
        }

        stage('Build React App') {
            steps {
                dir('welcome-react') {
                    sh 'npm run build'
                }
            }
        }
    }

    post {
        success {
            echo '✅ React build successful 🎉'
        }
        failure {
            echo '❌ Build failed'
        }
    }
}
