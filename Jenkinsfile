pipeline {
    agent any

    stages {
        stage('Deploy') {
            steps {
                sshagent(['ec2-key']) {
                    sh '''
                    ssh -o StrictHostKeyChecking=no ubuntu@54.234.215.60 "
                    CONTAINER_ID=\$(docker ps -q)
                    if [ ! -z \"\$CONTAINER_ID\" ]; then
                        docker stop \$CONTAINER_ID
                        docker rm \$CONTAINER_ID
                    fi
                    docker run -d -p 80:80 -v /home/ubuntu/app:/usr/share/nginx/html nginx
                    "
                    '''
                }
            }
        }
    }
}
