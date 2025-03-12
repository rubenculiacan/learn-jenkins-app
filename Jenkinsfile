pipeline {
    agent any

    stages {
        stage('Build') {
            agent{
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
                    ls -la
                '''
            }
        }

        stage('Running Test'){
            steps{
                echo 'Test step in the Test Stage'
            }
        }
    }
}
