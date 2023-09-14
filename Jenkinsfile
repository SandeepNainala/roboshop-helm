pipeline {

  agent any

  parameters {
    string(name: 'component', defaultValue: '', description: 'App Component Name')
  }

  stages {

    stage ('Clone App Repo'){
      steps {
        dir ('APP'){
          git branch: 'main' , url: 'https://github.com/sandeepnainala/${component}'
      }
    }
  }

    stage('Helm Deploy'){
      steps{
        sh 'aws eks update-kubeconfig --name prod-eks-config'
        sh 'helm upgrade -i ${component} . -f APP/values.yaml'
      }
    }
  }
}