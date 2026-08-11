pipeline {
    agent any

    environment {
        ANSIBLE_HOST_KEY_CHECKING = 'False'
    }

    stages {
        stage('Run Ansible') {
            steps {
                sh '''
                    ansible-playbook  -i host.ini web.yaml
                '''
            }
        }
    }
}
