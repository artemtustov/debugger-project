#!groovy

import groovy.json.JsonSlurperClassic

node {
    def toolbelt = tool 'toolbelt'
    
    stage('Deploy to org'){
        //dir('D:\\atustov\\projects\\salesforce\\debugger-project') {
            withCredentials([file(credentialsId: 'Brave_Shark_Auth_file', variable: 'authFile')]) {
                bat "${toolbelt}/sf org login sfdx-url --sfdx-url-file ${authFile}"
                bat "${toolbelt}/sf project deploy start --target-org artem.tustov@wise-panda-qh200a.com"
            }
        }
    }
}
