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
                    sh "docker build -t aliahsan123/java-maven-app:1.0 ."
                }
            }
        }
        stage("Push to docker hub"){
            steps{
                script{
                    withCredentials([usernamePassword(
                         credentialsId: "docker-cred",
                         usernameVariable: "USER",
                         passwordVariable: "PASS"
                    )]) {
                     sh "docker login -u '$USER' -p '$PASS'"
                     sh "docker image push aliahsan123/java-maven-app:1.0"

                    }
                }
            }
        }
    }

}