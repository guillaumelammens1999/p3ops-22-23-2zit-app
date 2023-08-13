node {
    stage('Test') {
        echo 'Hello, world!'
    }
}


// node {
//     // If needed, you can checkout your source code using the following:
//     // checkout scm

//     stage('Build') {
//         sh 'sudo docker-compose build'
//     }

//     stage('Testen') {
//         sh '''
//         sudo dotnet restore src/Server/Server.csproj
//         sudo dotnet restore tests/Domain.Tests/Domain.Tests.csproj
//         sudo dotnet test tests/Domain.Tests/Domain.Tests.csproj
//         '''
//     }

//     stage('Voorbereiding: Containers Neerhalen') {
//         sh 'sudo docker-compose down'
//     }

//     stage('Deployment naar Applicatieserver (Lokaal)') {
//         // Assuming you're using a Git-based source, the 'env' variable will have the branch name.
//         if (env.BRANCH_NAME == 'main') {
//             sh 'sudo docker-compose up -d'
//         }
//     }

//     // Uncomment and use the following if you need cloud deployment based on a specific branch.
//     // stage('Deployment naar Applicatieserver (Cloud)') {
//     //     if (env.BRANCH_NAME == 'productie') {
//     //         sh 'jouw-deployment-commando-voor-cloud'
//     //     }
//     // }
// }
