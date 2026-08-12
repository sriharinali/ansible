pipeline {
    agent any

    stages {
        stage('Install Java and Apache') {
            steps {
                withCredentials([
                    sshUserPrivateKey(
                        credentialsId: 'target-server-ssh-key', 
                        keyFileVariable: 'SSH_KEY',
                        usernameVariable: 'SSH_USER')])
                {
                sh '''
                    ansible-playbook  -i host.ini ansible.yaml  --private-key "$SSH_KEY" -u "$SSH_USER"
                '''
                }
            }
        }

    }
}