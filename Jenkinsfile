import groovy.json.JsonSlurper

def parseJson(payload) {
    def jsonSlurper = new JsonSlurper()
    def json = jsonSlurper.parseText(payload)
    return json
}
pipeline {
    agent any
    
    stages {
        stage('Extract JSON Data') {
            steps {
                script {
                    def payload = env.BODY
                    
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


