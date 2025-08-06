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
                bat 'nuget restore SNKRS.sln'
            }
        }

        stage('Build') {
            steps {
                echo 'Building .NET Framework project'
                bat '"C:\\Program Files (x86)\\Microsoft Visual Studio\\2019\\BuildTools\\MSBuild\\Current\\Bin\\MSBuild.exe" SNKRS.csproj /p:Configuration=Release'
            }
        }
    }
}
