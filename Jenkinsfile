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
                sshPublisher(publishers: [sshPublisherDesc(configName: 'Ansible', transfers: [sshTransfer(cleanRemote: false, excludes: '', execCommand: 'ansible-playbook -i hosts tomcat-setup.yml', execTimeout: 120000, flatten: false, makeEmptyDirs: false, noDefaultExcludes: false, patternSeparator: '[, ]+', remoteDirectory: '/opt/', remoteDirectorySDF: false, removePrefix: '', sourceFiles: '**/*.jar')], usePromotionTimestamp: false, useWorkspaceInPromotion: false, verbose: false)])
        }
        }
    }
}
