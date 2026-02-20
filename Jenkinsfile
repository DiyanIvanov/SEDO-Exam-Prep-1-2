pipeline{
    agent any
    stages{
        stage("Restore Dependancies"){
            when {
                expression {
                    return env.GIT_BRANCH == 'origin/main' || env.GIT_BRANCH.startsWith('origin/feature/')
                }
            }
            steps{
                bat 'dotnet restore'
            }
        }
        stage("Build App"){
            when {
                expression {
                    return env.GIT_BRANCH == 'origin/main' || env.GIT_BRANCH.startsWith('origin/feature/')
                }
            }
            steps{
                bat 'dotnet build --no-restore'
            }
        }
        stage("Test App"){
            when {
                expression {
                    return env.GIT_BRANCH == 'origin/main' || env.GIT_BRANCH.startsWith('origin/feature/')
                }
            }
            steps{
                bat 'dotnet test --no-build --verbosity normal'
            }
        }
    }
}
