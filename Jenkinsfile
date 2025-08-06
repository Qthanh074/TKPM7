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
        bat "${env.NUGET} restore SNKRS.csproj"
    }
}

stage('Build') {
    steps {
        bat "${env.MSBUILD} SNKRS.csproj /p:Configuration=Release"
    }
}

  }
}
