pipeline {
    agent any
    environment {
        // 'ansible-ssh-creds' is the Credential ID you saved in Jenkins
        SSH_KEYS = credentials('target-server-ssh-key')
    }

    stages {
        stage('Install Java and Apache') {
            steps {
                withCredentials([sshUserPrivateKey(credentialsId: 'target-server-ssh-key', keyFileVariable: 'SSH_KEY')])
                {
                sh '''
                    ansible-playbook  -i host.ini ansible.yaml 
                '''
                }
            }
        }

    }
}