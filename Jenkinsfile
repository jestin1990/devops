pipeline{
		agent any
			stages{
				stage('Compile stage'){
					steps{
						sh 'mvn clean compile'
					}
				}
				stage('Testing stage'){
					steps{
						sh 'mvn test'
					}
				}
				
				stage('Quality stage'){
					steps{
						parallel(
							a: {
								sh 'mvn pmd:pmd'
							
							},
							b: {
								sh 'mvn cobertura:cobertura'
							
							}
						)
						
					}
				}
				
				stage('Install Stage'){
					steps{
						sh 'mvn clean compile'
						 echo "success END"
					}
				}
			
			
			}
		
		}
