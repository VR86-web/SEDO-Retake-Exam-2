pipeline {
    agent any

    tools {
        dotnet 'dotnet-6'
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Restore dependencies') {
            steps {
                sh 'dotnet restore'
            }
        }

        stage('Build') {
            steps {
                sh 'dotnet build --no-restore --configuration Release'
            }
        }

        stage('Run tests') {
            steps {
                sh 'dotnet test --no-build --configuration Release'
            }
        }
    }
}
