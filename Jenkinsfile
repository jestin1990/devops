pipeline{
		agent any
			stages{
				stage('Compile stage'){
					steps{
						withMaven(maven : 'Maven_3.6.0')
							sh 'mvn clean compile'
					}
				}
				stage('Testing stage'){
					steps{
						withMaven(maven : 'Maven_3.6.0')
							sh 'mvn test'
					}
				}
				
				stage('Quality stage'){
					steps{
						parallel(
							a: {
								withMaven(maven : 'Maven_3.6.0')
								sh 'mvn pmd:pmd'
							
							},
							b: {
								withMaven(maven : 'Maven_3.6.0')
								sh 'mvn cobertura:cobertura'
							
							}
						)
						
					}
				}
				
				stage('Install Stage'){
					steps{
						withMaven(maven : 'Maven_3.6.0')
							sh 'mvn clean compile'
							echo "success END"
					}
				}
			
			
			}
		
		}
