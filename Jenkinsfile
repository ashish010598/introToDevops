pipeline {
    agent any
    triggers {
        githubPush()
    }
    stages {
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
            when {
                expression {
                    env.GIT_BRANCH != 'origin/master'
                }
            }
            steps {
                echo 'Deploying to Staging...'
                sh 'echo "Staging Deployment Done"'
            }
        }
        stage('Deploy to Production') {
            when {
                expression { env.GIT_BRANCH == 'origin/master' }
            }
            steps {
                echo 'Deploying to Production...'
                sh 'echo "Production Deployment Done"'
            }
        }
    }
}
