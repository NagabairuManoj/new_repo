import groovy.json.JsonSlurper

def response = httpRequest "http://18.142.244.1:8080/generic-webhook-trigger/invoke?token=authtoken"
node() {
    writeFile file: 'response.json', text: response.content
}
pipeline {
    agent any
    
    stages {
        stage('Extract JSON Data') {
            steps {
                script {
                    payload = readFile 'response.json'
                    
                    // Parse the JSON payload
                    def parsedPayload = parseJson(payload)
                    
                    // Extract the desired JSON fields
                    def repositoryUrl = parsedPayload.repository.url
                    def commitMessage = parsedPayload.head_commit.message
                    
                    // Use the extracted data in your pipeline steps
                    echo "Repository URL: ${repositoryUrl}"
                    echo "Commit Message: ${commitMessage}"
                }
            }
        }
    }
}


