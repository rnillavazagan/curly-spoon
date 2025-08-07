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

        stage('Deploy') {
            steps {
                echo 'Deploying...'
                sh 'echo "Pretending to deploy..."'
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
