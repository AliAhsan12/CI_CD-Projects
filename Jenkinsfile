pipeline{
    
    agent any 

    stages{
        stage("git checkout"){
            steps{
                script{
                    git 'https://github.com/AliAhsan12/CI_CD-projects.git'
                }
            }
        }
        stage("unit testing"){
            steps{
                script{
                    sh 'mvn clean test'
                }
            }
        }
         stage("Integration testing"){
            steps{
                script{
                    sh 'mvn verify -DskipUnitTests'
                }
            }
        }
         stage("Build"){
            steps{
                script{
                    sh 'mvn clean install'
                }
            }
        }
        stage("docker image build"){
            steps{
                script{

                }
            }
        }
    }

}