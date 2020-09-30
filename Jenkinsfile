pipeline {
    agent any
    
    tools {
        maven 'maven-local'
    }

    stages {
	    stage('Package') {
	        steps {
	            build job: 'Shopizer_01_Package' 
	        }
	    }

	    stage('Install') {
	        steps {
	            build job: 'Shopizer_02_Integration' 
	        }
	    }

	    stage('Selenium Tests') {
	        steps {
	            build job: 'Shopizer_03_Tests_IHM' 
	        }
	    }

	    stage('Unit Tests & SonarQube') {
	        steps {
	            build job: 'Shopizer_04_Tests_Unit_et_Qualimetrie' 
	        }
	    }

	    stage('NeoLoad') {
	        steps {
	            build job: 'Shopizer_05_Tests_Performance' 
	        }
	    }

	    stage('Deploy') {
	        steps {
	            build job: 'Shopizer_06_Deploiement' 
	        }
	    }
    }	
}
