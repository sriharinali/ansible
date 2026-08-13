pipeline {
    agent any

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
