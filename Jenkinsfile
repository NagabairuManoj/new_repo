pipeline {
    agent any
    
    stages {
        stage('Extract JSON Data') {
            steps {
                echo "start"
                def webhookVar = params.test_var
                echo "Webhook Variable: ${webhookVar}"
                echo "end"
            }
        }
    }
}


