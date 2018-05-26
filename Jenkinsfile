pipeline {
	agent any   
	stages {
        stage('Build') { 
            steps {
								sh 'cd umlet-standalone'
                sh 'mvn clean install' 
            }
        }
				stage('Test') {
						steps {
								sh 'cd umlet-standalone'
								sh 'mvn test'
						}
						post {
								always {
										junit 'umlet-standalone/target/surefire-reports/*.xml'
								}
						}
				}
				stage('Archive') {
						steps {
								archiveArtifacts artifacts: 'umlet-standalone/target/umlet-standalone-14.3.0-SNAPSHOT.zip'
						}
				}
    }
}