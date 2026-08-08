pipeline {

    agent { label 'JAVA8' }

    stages {

        stage('Cloning git repo from github') {
            steps {

                // Git checkout
                git branch: 'sprint1_develop',
                    url: 'https://github.com/mailrajesshre/game-of-life.git'
            }
        }

        stage('Building application') {
            steps {

                // Maven build
                sh 'mvn clean package'
            }
        }

        stage('Creating artifacts and junit report') {
            steps {

                // JUnit test results
                junit stdioRetention: '',
                      testResults: '**/surefire-reports/*.xml'

                // Archive WAR artifact
                archiveArtifacts artifacts: '**/*.war',
                                 followSymlinks: false
            }
        }
    }
}
