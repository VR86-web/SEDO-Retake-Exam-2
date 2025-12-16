pipeline {
    agent any

    stages {

        stage('Restore dependencies') {
            steps {
                bat 'dotnet restore'
            }
        }

        stage('Build') {
            steps {
                bat 'dotnet build --no-restore --configuration Release'
            }
        }

        stage('Run tests') {
            steps {
                bat 'dotnet test --no-build --configuration Release'
            }
        }
    }
}
