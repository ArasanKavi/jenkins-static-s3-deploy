pipeline {
    agent any
    stages {
      stage("Pushing build to s3 bucket") {
            steps {

                 withCredentials([[
                 $class: 'AmazonWebServicesCredentialsBinding',
                 
                 accessKeyVariable: 'AKIATSSXBUSZSIVDANE7',
                 secretKeyVariable: '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'
                ]]) {
                // AWS Code
                sh """   
                  
                    
            aws s3 cp ./jenkins-static-s3-deploy s3://bucketnewly--recursive 
            
          aws cloudfront create-invalidation --distribution-id E3N569NDVQ6CD8 --paths "/*"
                """
                }
            } 
        } 

    }
}
