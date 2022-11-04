node{

	withDockerContainer('python:2-alpine') {
		
		stage('Initial step - Memeriksa versi python') {
			sh 'python --version'
		
		}
		
		stage('Build') {
			checkout scm
			sh 'python -m py_compile sources/add2vals.py sources/calc.py'
		}
	
	}

}
