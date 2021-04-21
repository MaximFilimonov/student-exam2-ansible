pipeline {
    agent any
    options {
        timeout(time: 1, unit: 'HOURS')
        retry(3)
    }
    stages {
        stage('Run playbook') {
            steps {
                ansiblePlaybook(
                    credentialsId: 'ansible_ssh',
                    playbook: 'playbook.yml',
                    inventory: 'hosts'
                )
            }
        } 
        stage('Check http answer') {
            steps {
                ansiblePlaybook(
                    credentialsId: 'ansible_ssh',
                    disableHostKeyChecking: true,
                    playbook: 'test.yml',
                    inventory: 'hosts'
                )
            }
        }
    }
}
