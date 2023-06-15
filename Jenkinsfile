pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                echo "${params.test}"
                def test = params.test
                def jsonSlurper = new groovy.json.JsonSlurper()
                def parsedJson = jsonSlurper.parseText(test)
                def cloneUrl = parsedJson.repository.html_url
            }
        }
    }
}


