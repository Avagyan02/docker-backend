pipeline {
    agent any
    
    environment {
        // Define initial environment variables
        MY_VARIABLE = 'initial_value'
    }

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
                    env.MY_VARIABLE = sh(returnStdout: true, script: 'git rev-parse --short=12 HEAD').trim()
                    echo "Git Revision List: ${env.MY_VARIABLE}"
                }

                sh 'cd /var/jenkins_home/workspace | ls -la'
                sh 'docker build -t docker-backend .'
                // sh 'docker images' 
                sh "docker tag docker-backend samavgn02/docker-backend:${env.MY_VARIABLE}"
            }
        }
    }
}
