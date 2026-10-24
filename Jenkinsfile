pipeline {
    agent any

    stages {
        stage("Restore the project") {
            when {
                expression {
                    env.GIT_BRANCH == 'origin/main' ||
                    env.BRANCH_NAME == 'main'
                }
            }
            steps {
                bat "dotnet restore"
            }
        }

        stage("Build the project") {
            when {
                expression {
                    env.GIT_BRANCH == 'origin/main' ||
                    env.BRANCH_NAME == 'main'
                }
            }
            steps {
                bat "dotnet build --no-restore"
            }
        }

        stage("Test the project") {
            when {
                expression {
                    env.GIT_BRANCH == 'origin/main' ||
                    env.BRANCH_NAME == 'main'
                }
            }
            steps {
                bat "dotnet test --no-build --no-restore"
            }
        }
    }
}