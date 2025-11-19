pipeline{
  agent any
  tools{
    maven 'Maven'
  }
  stages{
    stage("Cleanup"){
      steps{
        sh "mvn --version"
      }      
    }

   
  }
  post{
    always{
      sh "mvn clean"
    }
    success{
      echo "========pipeline executed successfully ========"
    }
    failure{
      echo "========pipeline execution failed========"
    }
  }
}


