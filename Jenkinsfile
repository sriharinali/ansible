pipeline {
    agent any
    environment {
        // 'ansible-ssh-creds' is the Credential ID you saved in Jenkins
        SSH_KEYS = credentials('target-server-ssh-key')
    }

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Test Ansible Connection') {
            steps {
                sh '''
                    ansible all -i host.ini -m ping -u ubuntu --private-key=$SSH_KEYS
                '''
            }
        }

        stage('Install Java and Apache') {
            steps {
                sh '''
                    ansible-playbook -i host.ini ansible.yaml -u ubuntu --private-key=$SSH_KEYS
                '''
            }
        }

    }

    
}
