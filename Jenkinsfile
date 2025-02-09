pipeline {
    agent any

    environment {
        BUILD_TOOL = 'maven'
        DEPLOY_DIR = '/var/www/html/app'
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/tejashwiniam/task-1.git'
            }
        }

        stage('Build') {
            steps {
                script {
                   
                        sh 'mvn build'
                   
                       
                    
                }
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }

        stage('Deploy') {
            steps {
                sh 'cp -r target/*.war $DEPLOY_DIR/'
            }
        }
    }

    post {
        success {
            echo 'Pipeline executed successfully!'
        }
        failure {
            echo 'Pipeline failed! Check logs for details.'
        }
    }
}

