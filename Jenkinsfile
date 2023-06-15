pipeline {
    agent any
    
    stages {
        stage('Run Command') {
            steps {
                script {
                    sh "echo ${params.test} > hi.json"
                    def url = sh(script: "cat hi.json | sed -n -e 's/.*\"clone_url\":\"\\([^\"]*\\).*/\\1/p'", returnStdout: true).trim()
                    echo "The URL is: ${url}"
                }
            }
        }
    }
}

