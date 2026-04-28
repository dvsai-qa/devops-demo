stage('Deploy') {
    steps {
        sh '''
        rm -rf site
        mkdir site
        cp index.html site/

        docker stop devops-app || true
        docker rm devops-app || true

        docker run -d -p 8082:80 -v $(pwd)/site:/usr/share/nginx/html:ro --name devops-app nginx
        '''
    }
}
