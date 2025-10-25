pipeline{
    agent any

    stages{
        stage("Restore some Dependencies"){
            when {branch pattern: "(main|feature)", comparator: "REGEXP"}
            steps{
                bat 'dotnet restore'
            }
         
        }
        stage("Build the applcication"){
            when {branch pattern: "(main|feature)", comparator: "REGEXP"}
            steps{
                bat 'dotnet build --no-restore'
            }
         
        }
          stage("Run the tests"){
            when {branch pattern: "(main|feature)", comparator: "REGEXP"}
            steps{
                bat 'dotnet test --no-build --verbosity normal'
            }
         
        }
    }
  
}