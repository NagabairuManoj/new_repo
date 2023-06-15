pipeline {
    agent any
    
    stages {
        stage('Run Command') {
            steps {
                script {
                    "echo ${params.test} > hi.json"
                    "cat hi.json | grep 'clone_url'"
                }
            }
        }
    }
}

