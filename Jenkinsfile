pipeline {
    agent any
//     parameters {
//         choice(name: 'ENV', choices: ['dev','qa'], description: 'Choose Environment')
//         string(defaultValue: 'env1', name: 'file')
//     }
    stages {
//         stage ('multi test') {
//             steps {
//                     sh "echo 'succfsdess   master'"
//                     sh "git branch"
//             }
//         }
//         stage ('multi env dev') {
//             when {
//                 expression { params.ENV == 'dev' }
//             }
//             steps {
//                 script {
//                     load "./${params.file}.groovy"
// //                     sh "echo ${env.ECS_CLUSTER}"
//                 }
//             }
//         }
        stage ('multi env qa') {
//             when {
//                 expression { params.ENV == 'qa' }
//             }
            steps {
                script {
                    sh '''
                    current_version=$(awk -F'[ ="]+' '$1 == "version" { print $2 }' pyproject.toml)
                    to_add=0.1.0
                    new_version=$current_version + $to_add
                    echo `$new_version | bc`
                    sed -i /0.1.0/$new_version/g pyproject.toml
                    cat pyproject.toml
                    '''
                    
//                     load "./env2.groovy"
//                     sh "echo ${env.ECS_CLUSTER}"
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

// def echo_func(var){
//     sh "echo $var"
//     //add code for this method
// }
