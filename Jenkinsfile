pipeline {
    agent any

    stages {
        stage('Clone') {
            steps {
                git branch: 'main', url: 'https://github.com/shaikafren/jenkins-pipeline-demo.git'
            }
        }

        stage('Build') {
            steps {
                sh 'echo "📦 Building the application..."'
            }
        }

        stage('Test') {
            steps {
                sh 'echo "🧪 Running tests..."'
            }
        }

        stage('Deploy') {
            steps {
                sh 'echo "🚀 Deploying application..."'
            }
        }
    }
}

