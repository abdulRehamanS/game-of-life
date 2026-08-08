pipeline{


    agent { label 'nameoflable'}

    stages{

        stage{'Cloning git repo from github'
            steps{
                //git utl
                git branch: 'sprint1_develop', url: 'https://github.com/mailrajesshre/game-of-life.git'
            }
        }

        stage{'Build Package'
            steps{
                //mvn shell cmd
                sh 'mvn clean package'
            }
        }

        stage{'Creating artifacts and junit report'
            steps{
                //path to create artifact and junit report
                junit stdioRetention: '', testResults: '**/surefire-reports/*.xml'
                archiveArtifacts artifacts: '**/*.war', followSymlinks: false
            }
        }
    }
}
