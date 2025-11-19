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

    stage("Compile"){
      steps{
        sh "mvn compile"
      }      
    }

   
  }
  post{
    always{
      sh "mv clean"
    }
    success{
      echo "========pipeline executed successfully ========"
    }
    failure{
      echo "========pipeline execution failed========"
    }
  }
}


