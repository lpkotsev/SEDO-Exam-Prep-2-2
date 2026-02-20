pipeline{
    agent any
    stages{
        stage("Restore dependencies"){
            when {
                branch "main"
            }
            steps{
                sh "dotnet restore"
            }
        }

        stage("Build the project"){
            when {
                branch "main"
            }
            steps{
                sh "dotnet build --no-restore"
            }
        }

        stage("Run the tests"){
            when {
                branch "main"
            }
            steps{
                sh "dotnet test --no-build --verbosity normal"
            }
        }
    }
}