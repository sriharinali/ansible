pipeline {
    agent any
       environment {
        ANSIBLE_HOST_KEY_CHECKING = 'False'
    }

    stages {
        stage('Install Java and Apache') {
            steps {
                sh '''
                    ansible-playbook  -i host.ini ansible.yaml
                '''
                }
            }
        }

    }
