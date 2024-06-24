pipeline {
    agent any

    stages{
        stage('zip the file'){
            steps{
                sh 'zip ansible_${BUILD_ID}.zip * --exclude Jenkinsfile'
                sh 'ls -l'
            }
        }
        stage('upload artifacts to jfrog'){
            steps{
                sh 'curl -u<USERNAME>:<PASSWORD> -T \
                  ansible_${BUILD_ID}.zip \
                 "http://ec2-35-174-213-169.compute-1.amazonaws.com:8081/artifactory/ansible_${BUILD_ID}.zip"'
            }
        }
    }
}