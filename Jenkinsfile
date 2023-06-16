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
            environment {
                GIT_CREDENTIALS = credentials('5b5bc46c-c754-45a3-b6b4-ee52addb09bb')
            }
            steps {
                script {
                    def gitUrl = env.URL // Retrieve the URL from the environment variable
                    dir('workspace') {
                        withCredentials([usernamePassword(credentialsId: env.GIT_CREDENTIALS, usernameVariable: 'GIT_USERNAME', passwordVariable: 'GIT_PASSWORD')]) {
                            git url: gitUrl, branch: 'master', credentialsId: env.GIT_CREDENTIALS, username: env.GIT_USERNAME, password: env.GIT_PASSWORD
                        }
                    }
                }
            }
        }
    }
}
