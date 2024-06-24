pipeline{
    agent any

    stages{
        stage('zip the file'){
            steps{
                sh 'rm -rf *.zip || echo ""'
                sh 'zip -r ansible-${BUILD_ID}.zip * --exclude Jenkinsfile'
            }
        }
        stage('upload artifacts to jfrog'){
            steps{
                sh 'curl -uadmin:AP5CNW3E6mvDGwoPRSb2crkLwR2 -T \
                ansible-${BUILD_ID}.zip \
                "http://34.229.70.101:8081/artifactory/ansible/ansible-${BUILD_ID}.zip"'
            }
        }
    }

}