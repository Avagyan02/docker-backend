pipeline {
    agent any
    
    triggers {
        GenericTrigger(
            genericVariables: [
                [key: 'WEBHOOK_PAYLOAD', value: '$.payload']
            ],
            token: 'jenkins-token'
        )
    }
    
    stages {
        stage('Extract Payload Hash') {
            steps {
                script {
                    def payload = GenericWebhookUtils.getPostContent("${WEBHOOK_PAYLOAD}")
                    def payloadHash = payload.get('hash')
                    echo "Payload Hash: ${payloadHash}"
                }
            }
        }
    }
}
