pipeline {
    agent {
        node {
            label 'ec2-jenkins-agent'
        }
    }

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }

        stage('Docker') {
          agent {
            docker {
                image 'node:18-alpine'
                reuseNode true
            }
          }
            steps {
                sh '''
                    ls -la
                    node --version
                    npm --version
                    npm ci
                    npm run build
                '''
            }
        }
    }
}