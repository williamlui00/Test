pipeline{
    agent any
    environment{
        NEW_VERSION = '1.1'
        BRANCH_NAME = scm.branches[0].name
    }
    stages{
        stage("build"){
            steps{
                echo "Start build"
                echo "========stage build - steps ========"
                echo "BRANCH_NAME is ${BRANCH_NAME}"
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