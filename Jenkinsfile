pipeline {
    agent {any}
    options {
        timeout(time: 1, unit: 'HOURS')
        retry(3)
    }
    stages {
        stage('Run playbook') {
            steps {
#                ansiblePlaybook(
#                
#                )
            }
        }
        stage('Check http answer') {
            steps {
                ansiblePlaybook(
                    playbook: "test.yml"
                    inventory: "hosts"
                )
            }
        }
    }
}
