pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                withCredentials([usernamePassword(credentialsId: 'dockerhub', passwordVariable: 'pass', usernameVariable: 'user')]) {

                bat "docker build -t polybot-jenkins:v1 ."
                bat "docker login -u $user -p $pass"
                bat "docker push avibendersky/polybot-jenkins:v1"
                }
            }
        }
        stage('Stage II') {
            steps {
                bat 'echo "stage II..."'
            }
        }
        stage('Stage III ...') {
            steps {
                bat 'echo echo "stage III..."'
            }
        }
    }
}
