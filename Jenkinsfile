pipeline {
    agent any

    stages {
        stage('w/o docker') {
            steps {
                sh '''
                    echo 'Without Docker'
                    ls -la
                    touch countainer-no.txt
                '''
                
            }
        }
        stage('w/ docker') {
            agent {
                docker {
                   image 'node:18-alpine'
                   reuseNode true
                }
            }
            steps {
                sh '''
                    echo 'With Docker'
                    npm --version
                    ls -la
                    touch countainer-yes.txt
                '''
            }
        }
    }
}
