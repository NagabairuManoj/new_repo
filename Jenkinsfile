pipeline {
    agent any
    
    stages {
        stage('Run Command') {
            steps {
                script {
                    sh "echo ${params.test} > hi.json"
                    def url = sh(script: "clone_url=\$(cat hi.json | grep -oP 'clone_url:\\K\\S+' | cut -d' ' -f1); echo \$clone_url", returnStdout: true).trim()
                    echo "The URL is: ${url}"
                }
            }
        }
    }
}
