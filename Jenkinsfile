pipeline {
  agent any
  stages {
    stage('Clone') {
      steps {
        git branch: 'main', url: 'https://github.com/Qthanh074/TKPM7.git'
      }
    }
    stage('Restore packages') {
      steps {
        bat 'nuget restore SNKRS.sln'
      }
    }
    stage('Build') {
      steps {
        bat 'msbuild SNKRS.csproj /p:Configuration=Release'
      }
    }
  }
}
