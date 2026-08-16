pipeline {
    agent any
    environment {
    ANSIBLE_HOST_KEY_CHECKING = 'False'
}

    stages {
        stage('Install Java and Apache') {
            steps {
                withCredentials([
                    sshUserPrivateKey(
                        credentialsId: 'ssh-key',
                        keyFileVariable: 'SSH_KEY',
                        usernameVariable: 'SSH_USER'
                    )
                ]) {
                sh '''
                    ansible-playbook  -i host.ini ansible.yaml -u "$SSH_USER" --private-key="$SSH_KEY" 
                '''
                }
            }
        }

    }
