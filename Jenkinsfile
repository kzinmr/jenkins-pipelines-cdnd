pipeline {
  agent any
  stages {
    stage('Upload to AWS') {
      parallel {
        stage('Upload to AWS') {
          steps {
            sh 'echo "Upload to AWS"'
            withAWS(region: 'us-west-2', credentials: 'aws-static') {
              s3Upload(pathStyleAccessEnabled: true, payloadSigningEnabled: true, file: 'index.html', bucket: 'jenkins-pipeline-cdnd-kzinmr')
            }

          }
        }

        stage('Lint HTML') {
          steps {
            sh 'tidy -q -e *.html'
          }
        }

      }
    }

  }
}