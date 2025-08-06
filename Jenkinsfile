environment {
  MSBUILD = '"C:\\Program Files\\Microsoft Visual Studio\\2022\\Community\\MSBuild\\Current\\Bin\\MSBuild.exe"'
  NUGET   = '"C:\\Tools\\nuget\\nuget.exe"'
}

pipeline {
  agent any
  environment {
    MSBUILD = "${MSBUILD}"
    NUGET   = "${NUGET}"
  }
  stages {
    stage('Clone') {
      steps {
        git branch: 'main', url: 'https://github.com/Qthanh074/TKPM7.git'
      }
    }
    stage('Restore packages') {
      steps {
        bat "${env.NUGET} restore SNKRS.sln"
      }
    }
    stage('Build') {
      steps {
        bat "${env.MSBUILD} SNKRS.csproj /p:Configuration=Release"
      }
    }
  }
}
