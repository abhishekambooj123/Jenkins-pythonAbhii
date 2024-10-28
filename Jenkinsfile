pipeline {
    agent any
    environment {
        // Define any environment variables here
        PYTHON_VERSION = '3.9'  // Example: Specify Python version
    }
    stages {
        stage('Clone Repository') {
            steps {
                // Replace URL with your repository URL
                git 'https://github.com/your-username/your-python-repo.git'
            }
        }
        
        stage('Set Up Environment') {
            steps {
                // Install dependencies
                sh 'python3 -m venv venv'
                sh './venv/bin/pip install --upgrade pip'
                sh './venv/bin/pip install -r requirements.txt'
            }
        }
        
        stage('Run Tests') {
            steps {
                // Run tests using pytest or another testing tool
                sh './venv/bin/python -m pytest tests/'
            }
        }
        
        stage('Lint Code') {
            steps {
                // Run linter, e.g., flake8
                sh './venv/bin/flake8 src/'
            }
        }
        
        stage('Build') {
            steps {
                // Run build step if necessary
                echo 'Build step here if needed'
            }
        }
        
        stage('Deploy') {
            steps {
                echo 'Deployment step here if needed'
            }
        }
    }
    post {
        always {
            // Clean up or notify
            echo 'Pipeline completed!'
        }
    }
}
