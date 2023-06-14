pipeline {
  agent any
  
  stages {
    stage('Extract JSON Data') {
      steps {
        script {
          def payload = readJSON text: env.BODY

          // Extract the desired JSON fields from the payload
          def repositoryUrl = payload.repository.url
          def commitMessage = payload.head_commit.message

          // Use the extracted data in your pipeline steps
          echo "Repository URL: ${repositoryUrl}"
          echo "Commit Message: ${commitMessage}"
        }
      }
    }
  }
}

