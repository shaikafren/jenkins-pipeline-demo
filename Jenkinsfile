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
                // Add your actual build commands here if needed, e.g., npm install, mvn package
            }
        }

        stage('Test') {
            steps {
                sh 'echo "🧪 Running tests..."'
                // Add your actual test commands here if needed
            }
        }

        stage('Docker Build') {
            steps {
                sh 'echo "🐳 Building Docker image..."'
                sh 'docker build -t myapp:latest .'
            }
        }

        stage('Docker Run') {
            steps {
                sh 'echo "▶️ Running Docker container..."'
                sh 'docker run -d -p 8080:8080 --name myapp-container myapp:latest || docker restart myapp-container'
            }
        }

        stage('Deploy') {
            steps {
                sh 'echo "🚀 Deployment stage completed!"'
                // If you have a real deployment, add commands here (e.g., copy to server, kubectl apply, etc.)
            }
        }
    }
}
