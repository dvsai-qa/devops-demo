pipeline {
    agent any

    stages {
        stage('Deploy') {
            steps {
                sshagent(['ec2-key']) {
                    sh '''
                    ssh -o StrictHostKeyChecking=no ubuntu@54.234.215.60 "
                    docker kill \$(docker ps -q) 2>/dev/null || true
                    docker rm \$(docker ps -aq) 2>/dev/null || true
                    docker run -d -p 80:80 -v /home/ubuntu/app:/usr/share/nginx/html nginx
                    "
                    '''
                }
            }
        }
    }
}
