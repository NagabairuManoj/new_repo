pipeline {
    agent any
    
    stages {
        stage('Run Command') {
            steps {
                script {
                    sh "echo ${params.test} > hi.json"
                    def url = sh(script: "cat hi.json | grep -oP 'clone_url:\\\\K\\\\S+' | cut -d' ' -f1", returnStdout: true).trim()
                }
            }
        }
    }
}

