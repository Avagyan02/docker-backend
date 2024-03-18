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
                    def commitHash = (git rev-parse --short=12 HEAD)
                    echo "Git Revision List: ${commitHash}"
                }
            }
        }
    }
}
