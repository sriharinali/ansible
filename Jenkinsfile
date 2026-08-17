pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Ansible Ping Test') {
            steps {
                sh '''
                    echo "Running Ansible ping test..."
                    ansible-playbook -i host.ini ping.yaml
                '''
            }
        }
    }

    post {
        success {
            echo 'Ansible ping test completed successfully!'
        }

        failure {
            echo 'Ansible ping test failed!'
        }
    }
}