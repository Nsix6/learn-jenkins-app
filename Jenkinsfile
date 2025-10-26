pipeline {
    agent any

    stages {
        stage('Build') {
            agent {
                docker {
                    image 'node:18-alpine'
                    reuseNode true
                }
            }
            steps {
                sh '''
                    ls -la
                    node -v
                    npm -v
                    mkdir -p .npm-cache
                    npm config set cache .npm-cache --global
                    npm ci
                    npm run build
                '''
            }
        }
    }
}