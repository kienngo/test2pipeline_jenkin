pipeline {
    agent any

    environment {
        dotnet = 'C:\\Program Files\\dotnet\\dotnet.exe'
    }
	
	options {
		skipDefaultCheckout()
	}

    stages {
	stage('Checkout source code') {
	    steps {
		git branch: 'master',
		url: 'http://10.32.4.160:3080/root/kaimamvrs.git'
	    }
	}
    }
}
