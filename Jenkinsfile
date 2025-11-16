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

        stage('Docker Build') {
            steps {
                sh 'docker build -t myapp:latest .'
            }
        }

        stage('Docker Run') {
            steps {
                sh 'docker run -d -p 8080:80 myapp:latest'
            }
        }

        stage('Deploy') {
            steps {
                sh 'echo "🚀 Deploying application..."'
            }
        }
    }
}
