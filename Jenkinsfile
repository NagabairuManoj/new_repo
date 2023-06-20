pipeline {
    agent any
    stages {
        stage('Run Command') {
            steps {
                script {
                    sh "echo ${params.test} > hi.json"
                    def url = sh(script: "clone_url=\$(cat hi.json | grep -oP 'ssh_url:\\K\\S+' | cut -d' ' -f1); echo \$clone_url", returnStdout: true).trim()
                    echo "The URL is: ${url}"
                    env.URL = url // Store the URL in an environment variable for later use
                }
            }
        }
        stage('Git Checkout') {
            steps {
                git branch: 'master', credentialsId: '5b5bc46c-c754-45a3-b6b4-ee52addb09bb', url: env.URL
            }
        }
    }
}
