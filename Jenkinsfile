pipeline {
    
 agent any
    stages{
        
        stage ('Tests') {
		steps {
			parallel ( "unit tests": { sh 'echo  "mvn test"' },
                    "integration tests": { sh 'echo "mvn integration-test"' }
                )
        }
	}
      	stage ('Deploy') {
		steps {
            		sh "python code_holder/helloworld.py"
		}
      	}
	stage ('artifact') {
		steps {
            		sh "tar -zcvf code_holder.tar.gz code_holder"
		}
      	}    
    } 
 
 }
