pipeline {
    agent any
    stages {
        stage('Upload to AWS') {
            steps {
                sh 'echo "Upload to AWS"'
                withAWS(region:'us-west-2') {
                    s3Upload(file:'index.html', bucket:'static', path:'index.html')
                }
            }
        }
    }
}