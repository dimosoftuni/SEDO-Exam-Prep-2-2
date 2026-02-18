pipeline {
    agent any
    stages{
        stage("Restore dependencies"){
            when {
                expression {
                    return env.GIT_BRANCH == 'origin/main'
                }
            }
        }
        stage("Build the project"){
            when {
                expression {
                    return env.GIT_BRANCH == 'origin/main'
                }
            }
                        steps{
                bat "dotnet build --no-restore"
            }
        }
        stage("Run the tests"){
            when {
                expression {
                    return env.GIT_BRANCH == 'origin/main'
                }
            }
            steps{
                bat "dotnet test --no-build --verbosity normal"
            }
        }
    }
}