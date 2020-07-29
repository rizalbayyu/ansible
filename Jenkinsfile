pipeline {
    agent any

    stages {
        stage('Clone Ansible Project') {
            steps {
                git 'https://github.com/rizalbayyu/ansible'
            }
        }
        stage('Execute Playbook Prepare') {
            steps {
                ansiblePlaybook credentialsId: 'test3', disableHostKeyChecking: true, installation: 'Install Service', inventory: 'hosts', playbook: 'ansible/prepare.yml'
            }
        }
        stage('Execute Playbook Owncloud') {
            steps {
                ansiblePlaybook credentialsId: 'test3', disableHostKeyChecking: true, installation: 'Install Service', inventory: 'hosts', playbook: 'ansible/owncloud.yml'
            }
        }
        stage('Execute Playbook Monitoring') {
            steps {
                ansiblePlaybook credentialsId: 'test3', disableHostKeyChecking: true, installation: 'Install Service', inventory: 'hosts', playbook: 'ansible/Monitoring.yml'
            }
        }
        stage('Execute Playbook Logging') {
            steps {
                ansiblePlaybook credentialsId: 'test3', disableHostKeyChecking: true, installation: 'Install Service', inventory: 'hosts', playbook: 'ansible/logging.yml'
            }
        }
        stage('Execute Playbook nginx') {
            steps {
                ansiblePlaybook credentialsId: 'test3', disableHostKeyChecking: true, installation: 'Install Service', inventory: 'hosts', playbook: 'nginx/nginx.yml'
            }
        }
    }
}
