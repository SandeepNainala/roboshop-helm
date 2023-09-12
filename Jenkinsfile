pipeline {

  agent any

  stages {

    stage ('Clone App Repo'){
      dir ('APP'){
        git branch: 'main' , url: 'https://github.com/sandeepnainala/cart'
      }
    }

    stage('Helm Deploy'){
      sh 'helm upgrade -i ${component} . APP/values.yaml'
    }

  }

}