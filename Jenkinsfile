pipeline {
    agent any
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
        stage('Docker Push') {
            steps {
                withCredentials([usernamePassword(passwordVariable: 'Personiv@123$', usernameVariable: 'ar8888')]) {
                    sh 'docker login -u $ar8888 -p $Personiv@123$'
                    sh 'docker tag ar8888/pro:1.0'
                    sh 'docker push ar8888/pro:1.0'
                    sh 'docker logout'
                }
            }
        }
    }
}
