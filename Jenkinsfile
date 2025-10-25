pipeline {
    agent any

    stages {
        stage('no docker') {
            steps {
                sh '''
                echo "without docker"
                ls -la
                touch container-no.txt
                '''
            }
        }

        stage('docker') {
            agent {
                docker {
                    image 'node:18-alpine'
                    reuseNode true
                }
            }
            steps {
                sh '''
                echo "with docker"
                ls -la
                touch container-yes.txt
                '''
            }
        }
    }
}
