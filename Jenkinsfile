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
        stage ('multi env dev') {
            when {
                expression { params.ENV == 'dev' }
            }
            steps {
                script {
                    load "./env1.groovy"
//                     sh "echo ${env.ECS_CLUSTER}"
                }
            }
        }
        stage ('multi env qa') {
//             when {
//                 expression { params.ENV == 'qa' }
//             }
            steps {
                script {
//                     load "./env2.groovy"
                    sh "echo ${env.ECS_CLUSTER}"
//                     echo_func(env.ECS_CLUSTER)
                }
            }
        }
//         stage ('multi env qa') {
//             when {
//                 expression { params.ENV == 'qa' }
//             }
//             steps {
//                 script {
//                     load "./env2.groovy"
// //                     sh "echo ${env.ECS_CLUSTER}"
//                     echo_func(env.ECS_CLUSTER)
//                 }
//             }
//         }
    }
}

def echo_func(var){
    sh "echo $var"
    //add code for this method
}
