pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main',
                url: 'https://github.com/Raunak-Dehankar/IndexPage.git'
            }
        }

        stage('Build WAR') {
            steps {
                bat '''
                jar -cvf Index_page.war *
                '''
            }
        }

        stage('Archive') {
            steps {
                archiveArtifacts artifacts: '*.war', fingerprint: true
            }
        }
    }
}