
pipeline {
    agent any
    options {
        timestamps()
    }
    environment {
      CICD_URL="https://raw.githubusercontent.com/RedHatInsights/cicd-tools/main"
    }

    stages {
        stage('Clone Git Repository') {
            steps {
/*            
                script {
                    GIT_COMMIT_HASH = ghprbActualCommit.take(6)
                }
*/                
                checkout scmGit(
                    branches: [[name: '$ghprbSourceBranch']],
                    userRemoteConfigs: [[url: '$ghprbAuthorRepoGitUrl']])
//                stash(name: 'project-files', includes: "**")
            }
        }

        stage('Dummy') {
            steps {
              echo "hello!"
            }
        }
    }
}
