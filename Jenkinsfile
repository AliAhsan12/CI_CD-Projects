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
        stage("unit test"){
            steps{
                script{
                    sh 'mvn test'
                }
            }
        }
    }

}