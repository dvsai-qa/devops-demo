pipeline {
    agent any

    stages {
        stage('Deploy to EC2') {
            steps {
                sshagent(['ec2-key']) {
                    sh '''
                    
                    # Copy latest index.html to EC2
                    scp -o StrictHostKeyChecking=no index.html ubuntu@54.234.215.60:/home/ubuntu/app/
                    
                    # Deploy container
                    ssh -o StrictHostKeyChecking=no ubuntu@54.234.215.60 "
                    docker stop \$(docker ps -q) || true
                    docker rm \$(docker ps -aq) || true
                    docker run -d -p 80:80 -v /home/ubuntu/app:/usr/share/nginx/html nginx
                    "
                    
                    '''
                }
            }
        }
    }
}
