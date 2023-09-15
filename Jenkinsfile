

pipeline {
    agent any
    stages {
        stage ('Git Clone') {
            steps {
                git url: 'https://github.com/user/repo.git'
            }
        }
        stage ('Copy File to S3') {
            steps {
                withAWS(region:'us-east-1', credentials:'aws-jenkins-demo') {
                    s3Upload(file:'Code/index.html', bucket:'jenkin-s3', path:'index.html')
                }
            }
        }
    }
}