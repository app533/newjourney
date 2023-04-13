pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'docker build -t tmujee200/dockerfile .'
            }
        }
        stage('Test') {
            steps {
                sh 'docker run --rm tmujee200/dockerfile echo "Container launched successfully"'
            }
        }
        stage('PUSH') {
            steps {
                withCredentials([usernamePassword(credentialsId: '<fordocker>', passwordVariable: 'tmujee200', usernameVariable: 'alladin 098')]) {
                    sh 'docker login -u $DOCKER_USERNAME -p $DOCKER_PASSWORD'
                    sh 'docker push tmujee200/dockerfile'
                }
            }
        }
    }

}
