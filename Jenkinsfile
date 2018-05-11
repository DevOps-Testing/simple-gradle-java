pipeline {
    agent {
        docker {
            image 'gradle:alpine' 
            args '-v /root/.gradle:/root/.gradle' 
        }
    }
    stages {
        stage('Build') { 
            steps {
                sh 'echo Building' 
            }
        }
        stage('Test') {
            steps {
                sh 'echo Testing'
            }
            post {
                always {
                    junit 'target/surefire-reports/*.xml'
                }
            }
        }
        stage('Deliver') { 
            steps {
                sh 'Delivering' 
            }
        }
    }
}
