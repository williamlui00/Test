pipeline{
    agent any
    environment{
        NEW_VERSION = '1.1'
    }
    stages{
        stage("build"){
            when {
                expression {
                    env.BRANCH_NAME == 'main'
                }
            }
            steps{
                echo "Start to build"
                echo "========stage build - steps ========"
                echo "End of build"
            }
        }
        stage("test"){
            steps{
                echo "========stage test - steps ========"
            }
        }
        stage("deploy"){
            steps{
                echo "========stage deploy - steps ========"
                echo "The new version is ${NEW_VERSION}"
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