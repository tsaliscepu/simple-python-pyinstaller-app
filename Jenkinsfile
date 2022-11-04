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
	
	withDockerContainer('qnib/pytest') {
		
		stage('Test') {
			checkout scm
			sh 'py.test --verbose --junit-xml test-reports/results.xml sources/test_calc.py'
			junit 'test-reports/results.xml'
		}
	}

}
