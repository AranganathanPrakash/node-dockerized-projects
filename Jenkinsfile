pipeline {
    agent any
    environment {
        DOCKERHUB_CREDENTIALS=credential('dockerhub')
        {
    stages{
        stage("checkout"){
            steps{
                checkout scm
            }
        }

        stage("Build Image"){
            steps{
                sh 'docker build -t my-node-app:1.0 .'
            }
        }
        stage('login') {
            steps {
                sh 'echo $DOCKER_CREDENTIALS_PSW | docker login -u $DOCKER_CREDENTIALS_USR --password-stdin'
             }
        }
        stage('push') {
            steps{
               sh  'docker push ar8888/my-node-app:1.0'
            }
        }   
    
    }
}
