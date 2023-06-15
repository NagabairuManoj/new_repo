pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                script {
                    def test = params.test
                    if (test) {
                        def jsonSlurper = new groovy.json.JsonSlurper()
                        def parsedJson = jsonSlurper.parseText(test)
                        def cloneUrl = parsedJson.repository.html_url

                        println "Clone URL: ${cloneUrl}"
                    } else {
                        println "The 'test' variable is empty or null"
                    }
                }
            }
        }
    }
}
