pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'master',
                    url: 'https://github.com/vinodshivkumar4/demofinlaansible.git',
                    credentialsId: 'ansible' // Git credentials if required
            }
        }

        stage('Ansible Deploy') {
            steps {
                // Use SSH Agent with the private key stored in Jenkins
                sshagent(['ansible-credential-id']) {
                    sh '''
                    ansible-playbook $WORKSPACE/deploy.yml
                    '''
                }
            }
        }
    }
}
