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
                sshPublisher(publishers: [sshPublisherDesc(configName: 'Ansible', transfers: [sshTransfer(cleanRemote: false, excludes: '', execCommand: '', execTimeout: 120000, flatten: false, makeEmptyDirs: false, noDefaultExcludes: false, patternSeparator: '[, ]+', remoteDirectory: '', remoteDirectorySDF: false, removePrefix: '', sourceFiles: 'ansible-playbook -i hosts tomcat-setup.yml')], usePromotionTimestamp: false, useWorkspaceInPromotion: false, verbose: false)])
            }
        }
    }
}
