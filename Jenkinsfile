pipeline {
    agent {
        label 'tcrookes-node-js'
    }
    stages {
        stage('Hello World Build') {
            agent{
                label 'jenkins-tcrookes-nodejs'
            }
        
            steps{
                echo 'Building node-js...'
                sh 'docker build . -t tcrookes/node-web-app'
            }
        }
        stage('Hello World Run') {
            agent{
                label 'jenkins-tcrookes-nodejs-testing'
            }
            steps{
                echo 'Running node-js...'
                sh 'docker run -p 49160:8000 -d tcrookes/node-web-app'
            }

        }
    }
}