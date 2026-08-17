pipeline {
    agent any

    stages {
        stage('Ansible Ping Test') {
            steps {
                sh '''
                    echo "===== System ====="
                    whoami
                    pwd

                    echo "===== Python ====="
                    python3 --version

                    echo "===== Ansible ====="
                    ansible --version

                    echo "===== Files ====="
                    ls -la

                    echo "===== Ping Test ====="
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