pipeline {
    agent any
    
    stages {
        stage('Process Webhook') {
            steps {
                script {
                    def webhookVar = params.test_var
                    
                    // Use the webhook variable in your pipeline steps
                    echo "Webhook Variable: ${webhookVar}"
                }
            }
        }
        
        // Other stages in your pipeline
    }
}



