pipeline {
    agent any

    stages {
        // stage('Statische Analyse/Linting') {
        //     steps {
        //         sh 'jouw-linting-commando'
        //     }
        // }

        stage('Build') {
            steps {
                sh 'sudo docker-compose build'
            }
        }

        stage('Testen') {
            steps {
                sh '''
                sudo dotnet restore src/Server/Server.csproj &&
                sudo dotnet restore tests/Domain.Tests/Domain.Tests.csproj  &&
                sudo dotnet test tests/Domain.Tests/Domain.Tests.csproj
                '''
            }
        }

        stage('Voorbereiding: Containers Neerhalen') {
            steps {
                sh 'sudo docker-compose down'
            }
        }

        stage('Deployment naar Applicatieserver (Lokaal)') {
            when {
                branch 'main'
            }
            steps {
                sh 'sudo docker-compose up -d'
            }
        }

        // stage('Deployment naar Applicatieserver (Cloud)') {
        //     when {
        //         branch 'productie'
        //     }
        //     steps {
        //         // Dit zou een ander script/commando zijn dat specifiek is voor cloud deployment.
        //         sh 'jouw-deployment-commando-voor-cloud'
        //     }
        // }
    }
}
