pipeline {
    agent any
    
    stages {
        stage('Run Command') {
            steps {
                script {
                    sh "echo ${params.test} > hi.json"
                    def url = sh(script: "cat hi.json | awk -F '\"clone_url\":\"|\"' '{print $2}'", returnStdout: true).trim()
                    echo "The URL is: ${url}"
                }
            }
        }
    }
}

