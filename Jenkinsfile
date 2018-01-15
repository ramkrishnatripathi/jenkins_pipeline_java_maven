node {
   // Mark the code checkout 'stage'....
   stage('Checkout') {
      //steps{
          git url: 'https://github.com/TTFHW/jenkins_pipeline_java_maven.git'
     // }   
   }
   // Get the maven tool.
   // ** NOTE: This 'M3' maven tool must be configured
   // **       in the global configuration.           
   
   // Mark the code build 'stage'....
   stage('Build') {
      // steps{
         def mvnHome = tool 'maven-3.0.3'
         // Run the maven build
         sh "${mvnHome}/bin/mvn -Dmaven.test.failure.ignore clean package"
         //step([$class: 'JUnitResultArchiver', testResults: '**/target/surefire-reports/TEST-*.xml'])
     //  }   
   }  

}  
   
stage('Deploy approval'){
      input "Deploy to prod?"
}

node {
       stage('deploy to prod'){
        echo "deploying"
       }
 }
