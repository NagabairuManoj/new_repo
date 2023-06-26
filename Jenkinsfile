pipeline {
    agent any
    stages {
        stage('Run Command') {
            steps {
                script {
                    sh "echo ${params.test} > repo.json"
                    def url = sh(script: "clone_url=\$(cat repo.json | grep -oP 'clone_url:\\K\\S+' | cut -d' ' -f1); echo \$clone_url", returnStdout: true).trim()
                    echo "The URL is: ${url}"
                    env.URL = url // Store the URL in an environment variable for later use
                    def repo_name = sh(returnStdout: true, script: "echo ${url} | awk -F/ '{ print \$(NF-0) }' | sed 's/\\.git\$//'").trim()
                    env.REPO_NAME = repo_name
                }
            }
        }
        stage('Git Checkout') {
            steps {
                dir("${env.REPO_NAME}"){
                 git branch: 'master', credentialsId: '5b5bc46c-c754-45a3-b6b4-ee52addb09bb', url: env.URL
                }
            }
        }
        stage('Get Directory Name') {
            steps {
                script {
                    def command = 'basename "$(pwd)"'
                    def result = sh(returnStdout: true, script: command).trim()
                    println "Directory name: ${result}"
                }
            }
        }
    }
}
