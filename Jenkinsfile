import groovy.json.JsonSlurper

def test = params.test
def jsonSlurper = new JsonSlurper()
def parsedJson = jsonSlurper.parseText(test)
def refValue = parsedJson.ref

println "Ref Value: ${refValue}"

// pipeline {
//     agent any
    
//     stages {
//         stage('Process Webhook') {
//             steps {
//                 script {
//                     //def webhookVar = params.test
                    
//                     // Use the webhook variable in your pipeline steps
//                     //echo "Webhook Variable: ${webhookVar}"
// //                     echo "Params: ${params.test}"
//                 }
//             }
//         }
        
//         // Other stages in your pipeline
//     }
// }



