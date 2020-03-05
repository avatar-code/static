pipeline {
  agent any
  stages {
    stage('Upload to AWS') {
      steps {
        withAWS(region: 'us-east-2', credentials: 'aws-static') {
          sh 'echo "Uploading HTML content to S3"'
            s3Upload(pathStyleAccessEnabled:true, payloadSigningEnabled:true, file:'index.html', bucket:'ud-static-jenkins')
        }
      }
    }
  }
}
