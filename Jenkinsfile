pipeline {
    agent any

    stages {
        stage('Teeraform install') {
            steps {
                sh '''
                 ansible-playbook -i host.ini terraform.yaml
                '''
            }
         }
    }

    
}