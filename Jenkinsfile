pipeline {
    agent any

    stages {
        stage('Clone') {
            steps {
                echo 'Cloning source code'
                git branch: 'main', url: 'https://github.com/Qthanh074/TKPM7.git'
            }
        }

        stage('Restore package') {
            steps {
                echo 'Restoring packages...'
                bat 'dotnet restore'
            }
        }

        stage('Build') {
            steps {
                echo 'Build project .NET Core'
                bat 'dotnet build --configuration Release'
            }
        }
    }
}
