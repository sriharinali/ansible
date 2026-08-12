pipeline {
    agent any

    stages {
        stage('Install Java and Apache') {
            steps {
                withCredentials([sshUserPrivateKey(credentialsId: 'target-server-ssh-key', keyFileVariable: 'SSH_KEY')])
                {
                sh '''
                    ansible-playbook  -i host.ini ansible.yaml  -u ubuntu --private-key "$SSH_KEY"
                '''
                }
            }
        }

    }
}