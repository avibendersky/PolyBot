pipeline {


    options{
    buildDiscarder(logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '', daysToKeepStr: '5', numToKeepStr: '10'))
    disableConcurrentBuilds()

    }
agent any
 //  agent {
 //   docker {
//         image 'jenkinsagent:latest'
//         args  '--user root -v /var/run/docker.sock:/var/run/docker.sock'
//     }
// }
//
    environment{
        SNYK_TOKEN = credentials('snyk-token')
    }
    stages {
        stage('Build') {
            steps {
                withCredentials([usernamePassword(credentialsId: 'dockerhub', passwordVariable: 'pass', usernameVariable: 'user')]) {

                bat "docker build -t avibendersky/polybot-jenkins:1.0.${env.BUILD_NUMBER} ."
                bat "docker login -u $user -p $pass"
                bat "docker push avibendersky/polybot-jenkins:1.0.${env.BUILD_NUMBER}"
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
