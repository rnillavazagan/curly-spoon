pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building...'
                sh 'sleep 3'
                sh 'echo "Hello from Build stage!"'
            }
        }

        stage('Test') {
            steps {
                echo 'Testing...'
                sh 'sleep 3'
                sh 'echo "Running some dummy tests..."'
            }
        }

        stage('Tag') {
            steps {
                echo 'Tagging...'
                sh 'sleep 3'
                sh 'echo "Running dummy tag..."'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying...'
                sh 'sleep 3'
                sh 'echo "Pretending to deploy..."'
                // Intentionally fail the build
                // sh 'exit 1'
            }
        }
        
    }
}
