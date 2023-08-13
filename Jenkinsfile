pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    sh "sudo docker-compose build"
                }
            }
        }

        stage('Tests') {
            steps {
                script {
                    sh '''
                    sudo dotnet restore src/Server/Server.csproj
                    sudo dotnet restore tests/Domain.Tests/Domain.Tests.csproj
                    sudo dotnet test tests/Domain.Tests/Domain.Tests.csproj
                    '''
                }
            }
        }

        stage('Voorbereiding: Containers Neerhalen') {
            steps {
                script {
                    sh "sudo docker-compose down"
                }
            }
        }

        stage('Voorbereiding: Containers opzetten') {
            steps {
                script {
                    sh "sudo docker-compose up -d"
                }
            }
        }
    }
}
