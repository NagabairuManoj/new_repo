pipeline {
    agent any
    
    stages {
        stage('Process Webhook') {
            steps {
                script {
                    def webhookVar = params.test
                    
                    // Use the webhook variable in your pipeline steps
                    echo "Webhook Variable: ${webhookVar}"
                    echo "Params: ${params}"
                }
            }
        }
        
        // Other stages in your pipeline
    }
}



