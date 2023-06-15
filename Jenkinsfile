// pipeline {
//     agent any
    
//     stages {
//         stage('Process Webhook') {
//             steps {
//                 import groovy.json.JsonSlurper
//                 def test = params.test
//                 def jsonSlurper = new JsonSlurper()
//                 def parsedJson = jsonSlurper.parseText(test)
//                 def refValue = parsedJson.ref

//                 println "Ref Value: ${refValue}"
//             }
//         }
        
//         // Other stages in your pipeline
//     }
// }

pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
    }
}


