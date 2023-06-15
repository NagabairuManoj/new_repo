pipeline {
    agent any
    
    stages {
        stage('Run Command') {
            steps {
                script {
                    // Run the command
                    def command = "echo \${params.test} | grep 'clone_url'"
                    def output = sh(script: command, returnStdout: true).trim()
                    
                    // Print the output
                    println "Command Output:"
                    println output
                }
            }
        }
    }
}

