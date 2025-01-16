pipeline {
    agent any

    stages {
        stage('Build') {
            agent{
                docker{
                    image 'node:22.13.0-alpine'
                    reuseNode true
                }
            }
            steps {
                sh '''
                 ls -la
                 node --version
                 npm --version
                 pwd
                 sudo npm cache clean --force
                 rm -rf node_modules package-lock.json
                 npm ci
                 npm run build 
                 ls -la
                '''
            }
        }
    }
}
