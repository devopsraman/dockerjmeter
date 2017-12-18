pipeline {
	   agent any
	   stages {
	      stage ('Run jmeter scripts on docker') {
	         
			  steps {
				  
				  //sh ' /usr/local/bin/docker rmi lazzurs/jmeter ' 
				     
				  //sh ' /usr/local/bin/docker pull lazzurs/jmeter '
				         
				  //sh '/usr/local/bin/docker ps'
				    //sh '/usr/local/bin/docker stop master '
				     //sh '/usr/local/bin/docker rm master'
				 //sh' /usr/local/bin/docker run -dit -v /tmp:/tmp -p 1000:1000 --name master lazzurs/jmeter /bin/bash '
				 //sh '/usr/local/bin/docker exec -t master /bin/bash -c "jmeter -n -t /tmp/MVP1.0MaxLTV.v2.jmx -l /tmp/jmeter1.jtl"'
				  //sh '/usr/local/bin/docker run --rm -dit -v /tmp:/tmp -p 8080:8080 --name master  lazzurs/jmeter  /bin/bash '
				  sh '/usr/local/bin/docker run --rm -dit -v /tmp:/tmp -p 8080:8080   lazzurs/jmeter  /bin/bash '
				  sh '/usr/local/bin/jmeter --version'
				  //sh '/usr/lcaol/bin/rm -rf /tmp/*.jtl'
				  sh '/usr/local/bin/docker exec -i master /bin/bash -c "jmeter -n -t /tmp/MVP1.0MaxLTV.v2.jmx -l /tmp/jmeter16.jtl" '
				    
				  //perfReport compareBuildPrevious: true, excludeResponseTime: true, modePerformancePerTestCase: true, modeThroughput: true, sourceDataFiles: '/tmp/*.jtl'
				  //sh ' rm -rf /tmp/*.jtl'  
				  //sh '/usr/local/bin/docker stop master '
				    //sh '/usr/local/bin/docker rm master'
				    
                                  
			  }
		}
		
		 stage('publish Jmeter Report'){
			 steps {
			   perfReport compareBuildPrevious: true, excludeResponseTime: true, modePerformancePerTestCase: true, modeThroughput: true, sourceDataFiles: '/tmp/*.jtl'
				  
				    // sh'rm -rf /tmp/*.jtl' 
				      //sh' /usr/local/bin/docker stop master' 
				      //sh '/usr/local/bin/docker rm master'
				  
			 }
		 }
		   
	 }
		   
	   
}
