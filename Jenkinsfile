pipeline {

  agent any

  stages {

    stage ('Clone App Repo'){
      steps {
        dir ('APP'){
          git branch: 'main' , url: 'https://github.com/sandeepnainala/cart'
      }
    }
  }

    stage('Helm Deploy'){
      steps{
        sh 'helm upgrade -i ${component} . -f APP/values.yaml'
      }
    }
  }
}