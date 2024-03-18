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
                    def commitHash = sh(returnStdout: true, script: 'git rev-list -n 1 HEAD').trim()
                    echo "Git Revision List: ${commitHash}"
                }
            }
        }
    }
}
