pipeline {
    agent any

    environment {
        DOTNET_VERSION_1 = '6.0.x'
        DOTNET_VERSION_2 = '8.0.x'
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Restore Dependencies') {
            steps {
                sh 'dotnet restore HouseRentingSystem.sln'
            }
        }

        stage('Build') {
            steps {
                sh 'dotnet build HouseRentingSystem.sln --no-restore'
            }
        }

        stage('Run Tests') {
            steps {
                sh 'dotnet test HouseRentingSystem.sln --no-build --verbosity normal'
            }
        }
    }
}
