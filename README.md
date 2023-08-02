# DeveopsProject
Build a JAVA application &amp; Deploy into Tomcat server using Pipeline script
pipeline{
        agent any
        
        stages{
             stage('Build'){
                 steps{
                 sh 'mvn clean package'
                 }
                 post{
                      success{
                            echo" archiving the artifacts"
                            archiveArtifacts artifacts: '**/target.war'
                             }
                      }
                }
                stage ('deploy to tomcat server') {
                
                }
              }
          }
