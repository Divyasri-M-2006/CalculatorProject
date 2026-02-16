pipeline{
  agent any
  triggers{
    githubPush()
  }
  stages{
    stage('Compile'){
      steps{
        bat 'javac Calculator.java'
      }
    }
    stage('Run'){
      steps{
        bat 'java Calculator 10 + 5'
      }
    }
  }
  post{
    success{
      archiveArtifacts artifacts: '*.class', fingerprint:true
    }
    failure{
      echo 'Build Failed'
    }
  }
}
