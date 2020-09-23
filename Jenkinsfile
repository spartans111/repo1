pipeline {
    agent any
    stages {
        stage ('bpmn tests') {
            steps {
                sshagent (credentials: ['bpm-deploy-key']) {
                    sh "git clone git@github.com:spartans111/repo2.git"
                    sh "Cloning repo2..........."
                    sh "Cloning Done!"
                }
            }
        }

    }
}
