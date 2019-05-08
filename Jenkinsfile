pipeline {
    parameters {
		string(name: 'P1', defaultValue: '0.0.0.0', description: 'P1')
        booleanParam(name: 'P2', defaultValue: true, description: 'P2')
    }
    
	agent any
	stages {		
		stage('greet') {
            steps{			
                withMaven(maven: 'maven-3.6.1', jdk: 'jdk-8u212') {
					sh 'mvn --version'
				}
				fileOperations([fileCreateOperation(fileContent: 'test', fileName: 'test.txt')])
				nodejs(nodeJSInstallationName: 'nodejs-8.10.0') {
				    sh 'node -v'
				}
			}
		}
	}
}
