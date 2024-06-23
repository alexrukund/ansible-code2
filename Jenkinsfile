pipeline {
    agent any

    stages{
        stage('zip the file'){
            steps{
                sh 'zip ansible_${BUILD_ID}.zip * --exclude Jenkinsfile'
                sh 'ls -l'
            }
        }
    }
}