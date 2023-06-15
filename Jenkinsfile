pipeline {
    agent any
    
    stages {
        stage('Run Command') {
            steps {
                script {
                    sh "echo ${params.test} > hi.json"
                    sh "cat hi.json | grep -oP 'clone_url:\K\\S+' | cut -d' ' -f1"
                }
            }
        }
    }
}

