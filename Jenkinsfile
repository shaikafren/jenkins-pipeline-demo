pipeline {
    agent any

    environment {
        DOCKER_IMAGE = 'myapp:latest'
    }

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/shaikafren/jenkins-pipeline-demo.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    sh "sudo docker build -t ${DOCKER_IMAGE} ."
                }
            }
        }

        stage('Run Docker Container') {
            steps {
                script {
                    // Stop & remove previous container if exists
                    sh '''
                    if [ $(sudo docker ps -aq -f name=myapp-container) ]; then
                        sudo docker stop myapp-container
                        sudo docker rm myapp-container
                    fi
                    '''
                    // Run new container
                    sh "sudo docker run -d --name myapp-container -p 3000:3000 ${DOCKER_IMAGE}"
                }
            }
        }
    }

    post {
        success {
            echo '✅ Deployment successful! Access the app at http://<EC2_PUBLIC_IP>:3000'
        }
        failure {
            echo '❌ Deployment failed!'
        }
    }
}
