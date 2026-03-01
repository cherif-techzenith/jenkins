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
                echo "Dependencies installed successfully!"
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