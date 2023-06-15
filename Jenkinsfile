pipeline {
    agent any
    
    stages {
        stage('Run Command') {
            steps {
                script {
                    sh "echo ${params.test} > hi.json"
                    def url = sh'grep -oP '"clone_url":"\K[^"]+' hi.json'
                    echo "The URL is: ${url}"
                }
            }
        }
    }
}

