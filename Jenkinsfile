pipeline{
    agent any

   triggers {
        pollSCM('H/5 * * * *') // Poll SCM every 5 minutes
    }
    
    stages{
        stage("Build .NET Project"){
            steps{
                bat 'dotnet build' // For Windows (per requirement no separate restore stage)
            }
        }
        stage("Run Unit and Integration Tests"){
            steps{
                bat 'dotnet test --no-build --verbosity normal' // For Windows
            }
        }
    }
}