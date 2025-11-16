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
                sh 'echo "🐳 Building Docker image..."'
                sh 'docker build -t myapp:latest .'
            }
        }

        stage('Deploy') {
            steps {
                sh 'echo "🚀 Deploying application..."'
                // Stop any existing container
                sh 'docker stop myappcontainer || true'
                sh 'docker rm myappcontainer || true'
                // Run the container
                sh 'docker run -d -p 3000:3000 --name myappcontainer myapp:latest'
            }
        }
    }
}
