

pipeline {
    agent any

    environment {
        region = 'us-east-1'
        credentials = 'aws-jenkins-demo'
        sourceFilePath = 'Code/index.html'
        s3BucketName = 'jenkin-s3'
    }

    stages {
        stage('Copy File') {
            steps {
                withAWS(region: region, credentials: credentials) {
                    sh 'aws s3 cp ${sourceFilePath} s3://${s3BucketName}'
                }
            }
        }
    }
}