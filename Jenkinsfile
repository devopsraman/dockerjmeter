pipeline {
	   agent any
	   stages {
	      stage ('Run jmeter scripts on docker') {
	         
			  steps {
				  sh ' /usr/local/bin/docker rm lazzurs/jmeter 
				  
				  sh ' /usr/local/bin/docker pull lazzurs/jmeter '
				  //sh '/usr/local/bin/docker ps'
				  
				 //sh' /usr/local/bin/docker run -dit -v /tmp:/tmp -p 1000:1000 --name master lazzurs/jmeter /bin/bash '
				 //sh '/usr/local/bin/docker exec -t master /bin/bash -c "jmeter -n -t /tmp/MVP1.0MaxLTV.v2.jmx -l /tmp/jmeter1.jtl"'
				  sh 'docker run -dit -v /tmp:/tmp -p 8080:8080 --name master  lazzurs/jmeter  /bin/bash
				  sh '/usr/local/bin/docker jmeter --version'
				  sh '/usr/local/bin/docker exec -it master /bin/bash -c "jmeter -n -t /tmp/MVP1.0MaxLTV.v2.jmx -l /tmp/jmeter10.jtl"
				  perfReport compareBuildPrevious: true, excludeResponseTime: true, modePerformancePerTestCase: true, modeThroughput: true, sourceDataFiles: '/tmp/jmeter10.jtl'

			  }
		}
		   
		   
	 }
		   
	   
}
