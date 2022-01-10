pipeline {
    agent {label 'terraform'} 
    stages  {
        stage('Clean workspace'){
            steps {
                cleanWs()
            }
        }
		
        stage ('git clone')
   		 {
            steps{
				sh'''
					echo "${WORKSPACE}"
					
					git clone https://github.com/hitechvenkadesh/terra.git
				
				'''
            }
        }
    
		stage ('terraform init') {
			steps{
	  
				sh'''
					
					cd /slave/workspace/hitechpipline/terra/
					
					terraform init
				   
				'''
			} // end of steps
		} //end of stage
		
		stage ('terraform plan') {
			steps{		
	  
				sh'''
					
					echo "${WORKSPACE}"
					
					terraform plan					
					
				'''
			} // end of steps
		} //end of stage
		
		stage ('terraform apply') {
			steps{
	  
				sh'''
					
					echo "${WORKSPACE}"
					
					terraform apply -auto-approve
				   
				'''
			} // end of steps
		} //end of stage
  }
}
