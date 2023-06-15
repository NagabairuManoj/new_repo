pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                script {
                    echo "${params.test}" | grep "clone_url"
                    
                }
            }
        }
    }
}
