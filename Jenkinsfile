def gv
pipeline{
    agent any
    environment{
        NEW_VERSION = '1.1'
        BRANCH_NAME = "${scm.branches[0].name}"
    }
    stages{
        stage('confirm build'){
            steps {
                script {
                    if (env.BRANCH_NAME =~ 'main') {
                        input(
                            id: 'confirmBuild',
                            message: 'Do you want to continue with the build?',
                            parameters: [
                                [$class: 'BooleanParameterDefinition', defaultValue: false, description: 'Continue build?']
                            ]
                        )
                        if (!env.confirmBuild) {
                            error('Build aborted by user')
                        }
                    }
                }
            }
        }
        stage("init"){
            steps{
                script{
                    gv = load "jenkins.groovy"
                }
            }
        }
        stage("build"){
            when{
                expression {
                    BRANCH_NAME =~ "main"
                }
            }
            steps{
                echo "Start build"
                echo "========stage build - steps ========"
                echo "BRANCH_NAME is ${BRANCH_NAME}"
                echo "GIT_BRANCH is ${GIT_BRANCH}"
                script{
                    gv.buildapp()
                }
                echo "End of build"
            }
        }
        stage("test"){
            steps{
                echo "Start test"
                echo "========stage test - steps ========"
                echo "End of test"
            }
        }
        stage("deploy"){
            steps{
                echo "Start deploy"
                echo "========stage deploy - steps ========"
                echo "The new version is ${NEW_VERSION}"
                echo "end of deploy"
            }
        }
    }
    post{
        always{
            echo "========always========"
        }
        success{
            echo "========pipeline executed successfully ========"
        }
        failure{
            echo "========pipeline execution failed========"
        }
    }
}