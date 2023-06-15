pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                script {
                def test = params.test
                import groovy.json.JsonSlurper
                def jsonSlurper = new JsonSlurper()
                def parsedJson = jsonSlurper.parseText(test)
                def cloneUrl = parsedJson.repository.html_url

                println "Clone URL: ${cloneUrl}"
                }
            }
        }
    }
}


