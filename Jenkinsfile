pipeline {
    agent any
    
    stages {
        stage('Run Command') {
            steps {
                script {
                    sh "echo ${params.test} > hi.json"
                    def url = sh(script: "cat hi.json | grep -oP '\"clone_url\":\"\\K[^\"]+' | awk '{print \$1}'", returnStdout: true).trim()
                    echo "The URL is: ${url}"
                }
            }
        }
    }
}

