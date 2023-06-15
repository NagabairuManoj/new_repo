import groovy.json.JsonSlurper

def parseJson(payload) {
    def jsonSlurper = new JsonSlurper()
    def json = jsonSlurper.parseText(payload)
    return json
}
def getRepoURL() {
  sh "git config --get remote.origin.url > .git/remote-url"
  return readFile(".git/remote-url").trim()
}
pipeline {
    agent any
    
    stages {
        stage('Extract JSON Data') {
            steps {
                script {
                    def payload = getRepoURL()
                    
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


