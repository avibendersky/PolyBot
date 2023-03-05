pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                withCredentials([usernamePassword(credentialsId: 'dockerhub', passwordVariable: 'pass', usernameVariable: 'user')]) {

                bat "docker build -t harta ."
                bat "docker login -u $user -p $pass"
                bat "docker image push harta:v0.1  "
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
