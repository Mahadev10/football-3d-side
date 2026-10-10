pipeline{
    agent any
    stages{
        stage('Build') {
            steps {
                sh 'ls'
                sh 'tar -cvf python-app.tar  *'
                sh 'tar -tvf ./python-app.tar'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing...'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying...'
            }
        }
    }
}