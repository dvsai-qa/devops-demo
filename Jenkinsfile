pipeline {
    agent any

    stages {
        stage('Clone') {
            steps {
                echo 'Cloning code from GitHub...'
            }
        }

        stage('Build') {
            steps {
                echo 'Building application...'
                sh 'echo Compiling project...'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                sh 'echo Test cases executed successfully'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying application...'
                sh 'echo Application deployed locally'
            }
        }
    }
}
