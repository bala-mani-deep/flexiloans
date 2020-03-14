pipeline {
    agent any

    stages {

        stage('Docker build'){
            steps{
                script{
                    docker.build('flexiloans')
                }
            }
        }

        stage('Docker push'){
            steps{
                script{
                    docker.withRegistry('https://348274457022.dkr.ecr.ap-south-1.amazonaws.com', 'ecr:ap-south-1:sathya-aws') {
                        docker.image('flexiloans').push("$currentBuild.number")
                    }
                }
            }
        }
    }
}
