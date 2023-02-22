pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                withCredentials([usernamePassword(credentialsId: 'avibendersky', passwordVariable: 'Ab414625', usernameVariable: 'user')]) {


                sh '''
                docker login --username $user --password $pass
                docker build ...
                docker tag ...
                docker push ...
           '''
                }
            }
        }
        stage('Stage II') {
            steps {
                sh 'echo "stage II..."'
            }
        }
        stage('Stage III ...') {
            steps {
                sh 'echo echo "stage III..."'
            }
        }
    }
}
