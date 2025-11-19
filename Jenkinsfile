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

    stage("Test"){
      steps{
        sh "mvn test"
      }      
    }

    stage("Package"){
      steps{
        sh "mvn package"
      }      
    }

    stage("Install"){
      steps{
        sh "mvn install"
      }      
    }
   
  }
  post{
    always{
      sh "mvn --version"
    }
    success{
      echo "========pipeline executed successfully ========"
    }
    failure{
      echo "========pipeline execution failed========"
    }
  }
}
