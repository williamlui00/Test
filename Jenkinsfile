pipeline{
    agent any

    stages{
        stage("build"){
            when {
                expression {
                    BRANCH_NAME == 'main'
                }
            }
            steps{
                echo "========stage build - steps ========"
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