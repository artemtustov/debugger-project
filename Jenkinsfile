#!groovy

import groovy.json.JsonSlurperClassic

node {
    def toolbelt = tool 'toolbelt'

    stage('Pool project') {
        // Получаем код из нашего Git-репозитория;
        git 'https://github.com/artemtustov/debugger-project.git'
    }
    
    stage('Deploy to org'){
            withCredentials([file(credentialsId: 'Brave_Shark_Auth_file', variable: 'authFile')]) {
                bat "${toolbelt}/sf org login sfdx-url --sfdx-url-file ${authFile}"
                bat "${toolbelt}/sf project deploy start --target-org artem.tustov@wise-panda-qh200a.com"
            }
    }
}
