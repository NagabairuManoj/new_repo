pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                script {
                    sh 'echo ${params.test} | grep "clone_url"'
                    
                }
            }
        }
    }
}
