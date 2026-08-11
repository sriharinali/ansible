pipeline {
    agent any
    environment {
        ANSIBLE_HOST_KEY_CHECKING = 'False'
    }
    stages {
        stage('Deploy with Ansible') {
            steps {
                withCredentials([sshUserPrivateKey(credentialsId: 'target-server-ssh-key', keyFileVariable: 'SSH_KEY')]) {
                    // Tell Ansible exactly where the injected key file lives
                    sh "ansible-playbook -i host.ini web.yaml --private-key=\$SSH_KEY -u ubuntu"
                }
            }
        }
    }
}
