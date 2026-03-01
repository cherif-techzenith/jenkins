pipeline{
    agent any

    tools{
        nodejs "NodeJS"
    }

    stages{
        stage("Checkout"){
            steps{
                echo "Checking out code..."
                git branch: 'main', credentialsId: 'jen-doc-git', url: 'https://github.com/cherif-techzenith/jenkins.git'
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
                // sh "npm audit --audit-level=high"
            }
        }

        stage("Test"){
            steps{
                echo "Running tests..."
                // sh "npm test"
            }
        }

        stage("Build"){
            steps{
                echo "Building Docker image..."
                // sh "docker build -t my-app ."
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
            // deleteDir()
        }

        failure{
            echo "Pipeline failed!"
        }
    }
}