pipeline {
    agent any

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
                bat '"C:\\Tools\\nuget\\nuget.exe" restore SNKRS.sln'
            }
        }

        stage('Build') {
            steps {
                echo 'Building .NET Framework project'
                bat '"C:\\Program Files\\Microsoft Visual Studio\\2022\\Community\\MSBuild\\Current\\Bin\\MSBuild.exe" SNKRS.csproj /p:Configuration=Release'
            }
        }
    }
}
