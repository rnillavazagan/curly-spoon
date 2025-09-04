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
                // Simulating a test failure (e.g., a dummy command that fails)
                script {
                    def testResult = sh(script: 'echo "Running some dummy tests..."; exit 1', returnStatus: true)
                    if (testResult != 0) {
                        echo 'Test failed, marking build as unstable...'
                        currentBuild.result = 'UNSTABLE'  // Marks the build as unstable
                    }
                }
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

    post {
        always {
            echo "This will run regardless of build result."
        }
        success {
            echo "This will run only if the build was successful."
        }
        unstable {
            echo "This will run only if the build was marked as unstable."
        }
        failure {
            echo "This will run only if the build failed."
        }
    }
}
