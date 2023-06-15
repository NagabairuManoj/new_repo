pipeline {
    agent any
    
    stages {
        stage('Run Command') {
            steps {
                script {
                    sh "echo ${params.test} > hi.json"
                    sh 'cat hi.json | grep clone_url '
                }
            }
        }
    }
}

