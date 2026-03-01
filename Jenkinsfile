pipeline{
    agent any

    tools{
        nodejs "node-24"
    }

    stages{
        stage("Checkout"){
            steps{
                echo "Checking out code..."
            }
        }

        stage("Install"){
            steps{
                echo "Installing dependencies..."
                sh "npm install"
            }
        }

        stage("Security scan"){
            steps{
                echo "Running security scan..."
                sh "npm audit --audit-level=high"
            }
        }

        stage("Test"){
            steps{
                echo "Running tests..."
                sh "npm test"
            }
        }

        stage("Build"){
            steps{
                echo "Building Docker image..."
                sh "docker build -t my-app ."
            }
        }

        stage("Deploy"){
            steps{
                echo "Deploying to Kubernetes..."
            }
        }
    }

    post{
        always{
            echo "Pipeline completed successfully!"
            deleteDir()
        }

        failure{
            echo "Pipeline failed!"
        }
    }
}