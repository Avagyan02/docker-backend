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
                    def commitHash = sh(returnStdout: true, script: 'git rev-parse --short=12 HEAD').trim()
                    echo "Git Revision List: ${commitHash}"
                }

                sh 'cd /var/jenkins_home/workspace | ls -la'
                sh 'docker build -t docker-backend .'
                sh 'docker images' 
            }
        }
    }
}
