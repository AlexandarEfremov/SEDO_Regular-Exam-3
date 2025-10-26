pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Restore .NET Packages') {
            steps {
                sh 'dotnet restore'
            }
        }

        stage('Build .NET Project') {
            steps {
                sh 'dotnet build --no-restore'
            }
        }

        stage('Run .NET Tests') {
            steps {
                sh 'dotnet test --no-build --verbosity normal'
            }
        }
    }
}
