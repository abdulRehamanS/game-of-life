pipeline {

    agent { label 'JAVA8' }

    stages {

        stage('Building application') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Creating artifacts and junit report') {
            steps {

                junit stdioRetention: '',
                      testResults: '**/surefire-reports/*.xml'

                archiveArtifacts artifacts: '**/*.war',
                                 followSymlinks: false
            }
        }
    }
}
