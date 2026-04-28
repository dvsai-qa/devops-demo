stage('Deploy') {
    steps {
        sh '''
        docker stop devops-app || true
        docker rm devops-app || true
        docker run -d -p 8082:80 -v $PWD:/usr/share/nginx/html:ro --name devops-app nginx
        '''
    }
}
