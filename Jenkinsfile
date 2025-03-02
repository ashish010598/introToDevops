pipeline {
    agent any
    triggers {
        githubPush()
    }
    stages {
        stage('Debug') {
            steps {
                sh 'env'
            }
        }
        stage('Build') {
            steps {
                echo 'Building application...'
            }
        }
        stage('Test') {
            steps {
                echo 'Running tests...'
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Deploying to Staging...'
                sh 'echo "Staging Deployment Done"'
            }
        }
        stage('Deploy to Production') {
            when {
                branch 'master'
            }
            steps {
                echo 'Deploying to Production...'
                sh 'echo "Production Deployment Done"'
            }
        }
    }
}
