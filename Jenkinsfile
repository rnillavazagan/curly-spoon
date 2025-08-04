pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building...'
                sh 'echo "Hello from Build stage!"'
            }
        }

        stage('Test') {
            steps {
                echo 'Testing...'
                sh 'echo "Running some dummy tests..."'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying...'
                sh 'echo "Pretending to deploy..."'
            }
        }
    }
}
