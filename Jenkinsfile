pipeline{
    agent any
    tools {
      maven 'Maven'
    }

    stages{
        stage("git clone"){
            steps{
                git credentialsId: 'github-user-passwd', url: 'https://github.com/royalnaveen9740/SeleniumWithCucucumber.git'
            }
            post{
                success{
                    echo "Repository is cloned successfully"
                }
                failure{
                    echo "Repository failed to clone"
                }
            }
        }
        stage("maven-verify"){
            steps{
              echo 'Running from Jenkinsfile'
              sh 'mvn compile'
            }
            post{
                success{
                    echo "Maven verify"
                }
                failure{
                    echo "Maven failed"
                }
            }  
          }

    }
}