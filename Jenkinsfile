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
                sshagent(['ansible-credential-id']) {
                    sh '''
                    ansible-playbook -i "172.31.93.97,172.31.92.212," deploy.yml -u ansible --ssh-extra-args="-o StrictHostKeyChecking=no"
                    '''
                }
            }
        }
    }
}
