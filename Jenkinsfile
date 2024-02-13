pipeline {
    agent any
    
    stages {
        stage('SCM Checkout A') {
            steps {
                echo 'SCM'
                git url: 'https://github.com/Anurag-Evervent/node-todo-cicd.git'
            }
        }

        stage('Build') {
            steps {
                // Install npm dependencies
                sh 'npm i -f'
            }
        }

        stage('Deploy') {
            steps {
                // run pm2 
                sh 'pm2 start app.js'
            }
        }
    }
}
