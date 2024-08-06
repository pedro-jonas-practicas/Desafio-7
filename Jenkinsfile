pipeline {
    agent { label 'ansible-controller' }
    environment {
        ANSIBLE_PRIVATE_KEY=credentials('ansible-controller-key') 
        ANSIBLE_CONFIG='ansible.cfg'
    }
    stages {
        stage('Run Ansible Playbook from Jenkins') {
            steps {
                sh 'ansible-playbook -i inventory.ini --private-key=$ANSIBLE_PRIVATE_KEY main.yml'
            }
        }
    }
}
