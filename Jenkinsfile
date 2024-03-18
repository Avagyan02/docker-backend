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

    parameters {
        string(name: 'PAYLOAD_HASH', defaultValue: '', description: 'Payload hash from webhook')
    }
    
    stages {
        stage('Extract Payload Hash') {
            steps {
                script {
                    // def payload = GenericWebhookUtils.getPostContent("${WEBHOOK_PAYLOAD}")
                    def payload = env.WEBHOOK_PAYLOAD_HASH
                    // def payloadHash = payload.get('hash')
                    echo "Payload Hash: ${payload}"
                }
            }
        }
    }
}
