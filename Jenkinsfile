pipeline {
    agent any
    stages {
        stage('Upload to AWS') {
            steps {
                sh 'echo "Upload to AWS"'
                withAWS(region:'us-west-2', credentials:'AKIATVT7BYV5XT3GKPIB') {
                    s3Upload(file:'index.html', bucket:'static', path:'index.html')
                }
            }
        }
    }
}