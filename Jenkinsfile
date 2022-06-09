pipeline{
  agent any
  stages{
        stage('version-control'){
                steps{
                        checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'github-id', url: 'https://github.com/etechDevops/jenkins-parallel-job.git']]])
                }
        }
    stage('parallel-job'){
      parallel{
        stage('sub-job1'){
          steps{
            echo 'action1'
          }
        }
        stage('sub-job2'){
          steps{
            echo 'action2'
          }
        }
        stage('sub-job3'){
            steps{
                echo 'action3'
            }
        }
      }
    }
    stage('parallel-job by Juliet'){
          parallel{
            stage('sub-job4'){
              steps{
                  sh 'ps -ef'
                }
              }
              stage('sub-job5'){
                steps{
                  sh 'du -h'
                }
              }
            }
          }
          stage('codebuild'){
              steps{
                  sh 'cat /etc/passwd'
        }
    }
  }
}

