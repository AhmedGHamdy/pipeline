
pipeline { 
   agent any 
      stages { 
	  stage('Lint HTML') { 
             steps {
		 sh 'tidy -q -e *.html'    
	     }
	  }
	  stage('UploadToAWS') { 
             steps { 
		     sh 'echo "Hello World"'
		     sh 'pwd'
		     sh '''
		       echo "Multiline steps test"
		       ls -lah
		     '''
		     withAWS(credentials: 'aws-static') {
                         s3Upload bucket: 'udacityproject2s3', includePathPattern: "*.html", workingDir: '.'
                    }
	     } 
	  } 
      } 
}