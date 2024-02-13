pipeline {
    agent any

    stages {
        stage('Pull Code') {
            steps {
                // Checkout code from the GitHub repository
                checkout([$class: 'GitSCM', branches: [[name: '*/Staging']], 
                          userRemoteConfigs: [[url: 'https://github.com/Anurag-Evervent/node-todo-cicd.git']]])
            }
        }

        stage('Install Dependencies') {
            steps {
                // Run npm install with --force flag
                sh 'npm install -f'
            }
        }

        stage('Start Application') {
            steps {
                // Assuming pm2 is installed globally, you can directly start the application
                sh 'pm2 start app.js'
            }
        }
    }

    post {
        always {
            // Clean up resources or do any other necessary post-processing steps
            echo "Pipeline execution completed."
        }
    }
}
