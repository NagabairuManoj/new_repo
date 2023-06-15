pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                   sh 'echo ${params.test} | grep "clone_url"'
            }
        }
    }
}
