pipeline {
	agent any   
	stages {
        stage('Build') { 
            steps {
                sh 'mvn clean install' 
            }
        }
				stage('Archive') {
						steps {
								archiveArtifacts artifacts: 'umlet-standalone/target/umlet-standalone-14.3.0-SNAPSHOT.zip'
						}
				}
    }
}