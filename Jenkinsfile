pipeline {
    agent any
    
    triggers {
        GenericTrigger(
            // genericVariables: [
            //     [key: 'WEBHOOK_PAYLOAD', value: '$.payload']
            // ],
            token: 'jenkins-token'
        )
    }
    
    stages {
        stage('Extract Payload Hash') {
            steps {
                script {
                    def gitRevListOutput = sh(script: 'git rev-list HEAD', returnStdout: true).trim()
                    echo "Git Revision List: ${gitRevListOutput}"
                }
            }
        }
    }
}
