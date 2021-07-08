pipeline {
    agent any
    parameters {
        choice(name: 'ENV', choices: ['dev','qa'], description: 'Choose Environment')
    }
    stages {
//         stage ('multi test') {
//             steps {
//                     sh "echo 'succfsdess   master'"
//                     sh "git branch"
//             }
//         }
        stage ('multi env') {
            when {
                expression { params.ENV == 'dev' }
            }
            steps {
                script {
                    load "./env1.groovy"
                    sh "echo ${env.ECS_CLUSTER}"
                }
            }
        }
    }
}
