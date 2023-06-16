pipeline {
    agent any

    stages {
        stage('Run Command') {
            steps {
                script {
                    sh "echo ${params.test} > hi.json"
                    def url = sh(script: "clone_url=\$(cat hi.json | grep -oP 'clone_url:\\K\\S+' | cut -d' ' -f1); echo \$clone_url", returnStdout: true).trim()
                    echo "The URL is: ${url}"
                    env.URL = url // Store the URL in an environment variable for later use
                }
            }
        }

        stage('Git Clone') {
            steps {
                script {
                    def gitUrl = env.URL // Retrieve the URL from the environment variable
                    dir('workspace') {
                        git url: gitUrl, branch: 'master' // Perform the git clone using the URL
                    }
                }
            }
        }
    }
}
