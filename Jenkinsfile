pipeline {
  agent any

  parameters {
    choice(name: 'PROFILE', choices: ['dev', 'prod'], description: 'Maven-Profil')
    choice(name: 'SKIP_TESTS', choices: ['true', 'false'], description: 'Tests überspringen?')
  }
  
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

    stage("Tests"){
      steps{
        sh "mvn test"
      }      
    }

    stage("Package"){
      steps{
        sh "mvn package"
      }      
    }

    stage('Build') {
      steps {
        sh "mvn clean package -P${PROFILE} -DskipTests=${SKIP_TESTS}"
      }
    }


    stage("Install"){
      steps{
        sh "mvn install"
      }      
    }

    stage("Dependency:Thre"){
      steps{
        sh "mvn dependency:tree"
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
