pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Checkout the code from GitHub
                git branch: 'main', url: 'https://github.com/maheshbommu/jenkins-webhook-demo.git'
                echo "Code checked out successfully!"
            }
        }

        stage('Run Python Script') {
            steps {
                echo "Running app.py..."
                sh 'python3 app.py'
            }
        }

        stage('Display HTML Content') {
            steps {
                echo "Showing contents of index.html..."
                sh 'cat index.html'
            }
        }
    }

    post {
        success {
            echo "Build completed successfully!"
        }
        failure {
            echo "Build failed."
        }
    }
}

