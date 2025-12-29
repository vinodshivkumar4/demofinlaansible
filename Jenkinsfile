pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'master',
                    url: 'https://github.com/vinodshivkumar4/demofinlaansible.git',
                    credentialsId: 'ansible'
            }
        }

        stage('Ansible Deploy') {
            steps {
                sh '''
                ansible-playbook deploy.yml
                '''
            }
        }
    }
}

