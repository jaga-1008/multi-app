pipeline{
    agent any
    stages{
        stage('maven build'){
            when {
                expression{
                    env.Branch_Name.equals("develop") ||
                    env.Branch_Name.startsWith("feature")
                }
                
            }
            steps{
                echo "building maven"
            }
        }
        stage('sonar analysis'){
            when {
                branch "develop"
            }
            steps{
                echo "sonarqube scanning..."
            }
        }
        stage('nexus upload'){
            when {
                branch "develop"
            }
            steps{
                echo "artifacts uploading tyo nexus..."
            }
        }
        stage('deploy to qa'){
            when {
                branch "qa"
            }
            steps{
                echo "deploying to quality..."
            }
        }
        stage('deploy to master'){
            when {
                branch "master"
            }
            steps{
                echo "deploying to production..."
            }
        }
    }
}