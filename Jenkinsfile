pipeline {
    agent any

    stages {
	    stage('Scm Checkout') {
		    steps {
			    checkout scm
		    }
	    }
	    stage('Dockerfile') {
		    steps {
			    sh 'docker build -t fazilniveus/mass-baseline -f docker-wrapper .'
		    }
	    }
			    
	    stage('Scanning') {
		    steps {
			    sh 'docker run -u zap -i -t your-user/mass-baseline mass-baseline.sh'
		    }
	    }
    }
}
