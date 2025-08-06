pipeline {
    agent any

    environment {
        MSBUILD = '"C:\\Program Files\\Microsoft Visual Studio\\2022\\Community\\MSBuild\\Current\\Bin\\MSBuild.exe"'
        NUGET   = '"C:\\Tools\\nuget\\nuget.exe"'
    }

    stages {
        stage('Clone') {
            steps {
                echo 'Cloning source code'
                git branch: 'main', url: 'https://github.com/Qthanh074/TKPM7.git'
            }
        }

        stage('Restore packages') {
            steps {
                echo 'Restoring NuGet packages...'
                bat "${env.NUGET} restore SNKRS.csproj"
            }
        }

        stage('Build') {
            steps {
                echo 'Building .NET Framework project'
                bat "${env.MSBUILD} SNKRS.csproj /p:Configuration=Release"
            }
        }
    }
}
