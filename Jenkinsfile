pipeline {
   agent any

   stages {
      stage('Hello') {
         steps {
            script{
               git branch: 'main', credentialsId: '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', url: 'https://github.com/Keval-kanpariya/for-jenkins.git'
          
               def filePath = readFile "${dev.env}/ Your File Location"                   
               def lines = filePath.readLines(1) 
               for (line in lines) {                                            
                  build(job: "anotherjob",
                        parameters:[$line]
                )// for
            } // script
         }// steps
      } // stage
   } // stages
} // pipeline
}
