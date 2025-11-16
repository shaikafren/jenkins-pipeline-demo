pipeline {
    agent any

    stages {
        stage('Clone') {
            steps {
                git 'https://github.com/<your-username>/jenkins-pipeline-demo.git'
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
