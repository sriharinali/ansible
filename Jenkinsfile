pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Test Ansible Connection') {
            steps {
                sh '''
                    ansible all -i host.ini -m ping
                '''
            }
        }

        stage('Install Java and Apache') {
            steps {
                sh '''
                    ansible-playbook -i host.ini ansible.yaml
                '''
            }
        }

    }

    
}
