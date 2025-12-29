pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'master',
                url: 'https://github.com/your-repo.git'
            }
        }

        stage('Ansible Deploy') {
            steps {
                sh '''
                cd ansible
                ansible-playbook -i inventory deploy.yml
                '''
            }
        }
    }
}

