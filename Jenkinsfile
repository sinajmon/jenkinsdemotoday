

pipeline {
    agent any
    stages {
        stage('Git clone') {
            steps {
                git url: 'https://github.com/MyGit/Code'
            }
        }
        stage('Copy file to S3') {
            steps {
                withAWS(region: 'us-east-1', credentials: 'aws-jenkins-demo') {
                    s3Upload(file:"Code/index.html", bucket: 'jenkin-s3')
                }
            }
        }
    }
}