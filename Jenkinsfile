pipeline{
    agent any
    stages{
        stage("sonar"){
            agent {
                docker {
                    image 'openjdk:11'
                }
            }
            steps{
               script{
                    withSonarQubeEnv(credentialsId: 'sonartoken'){
                            sh "chmod +x gradlew"
                            //sh "./gradlew sonarqube"
                            sh "./gradlew --warning-mode=all"
                    }
               }
            }
    
        }
    }

}
