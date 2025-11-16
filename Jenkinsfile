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
                // Map host port 8080 to container port 3000 (matches your Dockerfile)
                sh 'docker run -d -p 8080:3000 --name myapp-container myapp:latest || docker restart myapp-container'
            }
        }

        stage('Deploy') {
            steps {
                sh 'echo "🚀 Application deployed!"'
            }
        }
    }
}
