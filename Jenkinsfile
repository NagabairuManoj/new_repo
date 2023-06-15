pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                script {
                    echo "${params.test}"
                    def test = params.test
                    def jsonSlurper = new groovy.json.JsonSlurper()
                    def parsedJson = jsonSlurper.parseText(test)
                    def cloneUrl = parsedJson.repository.html_url

                    println "Clone URL: ${cloneUrl}"
                }
            }
        }
    }
}



