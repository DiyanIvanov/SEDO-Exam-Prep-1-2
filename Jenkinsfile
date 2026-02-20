pipeline{
    agent any
    stages{
        stage("Restore Dependancies"){
            when {
                branch 'feature'
                branch 'main'
            }
            steps{
                bat 'dotnet restore'
            }
        }
        stage("Build App"){
            when {
                branch 'feature'
                branch 'main'
            }
            steps{
                bat 'dotnet build --no-restore'
            }
        }
        stage("Test App"){
            when {
                branch 'feature'
                branch 'main'
            }
            steps{
                bat 'dotnet test --no-build --verbosity normal'
            }
        }
    }
}
