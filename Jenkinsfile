pipeline {
    agent any

    tools {
        // Install the Maven version configured and add it to the path.
        maven "maven_3_5_0"
    }

    stages {
        stage('Build') {
            steps {
            // Get some code from a GitHub repository
            git 'https://github.com/Pipeline-ESS/Tomcat_ansible.git'
        }
        }
        stage('deploy'){
            steps {
                ansiblePlaybook installation: 'ansible', inventory: 'hosts', playbook: 'tomcat-setup.yml'
        }
        }
    }
}
