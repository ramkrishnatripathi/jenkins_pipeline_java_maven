node {
   // Mark the code checkout 'stage'....
   stage 'Checkout' {
   
   git url: 'https://github.com/TTFHW/jenkins_pipeline_java_maven.git'
   }
   // Get the maven tool.
   // ** NOTE: This 'M3' maven tool must be configured
   // **       in the global configuration.           
   
   // Mark the code build 'stage'....
   stage 'Build' {
   def mvnHome = tool 'maven-3.0.3'
   // Run the maven build
   sh "${mvnHome}/bin/mvn -Dmaven.test.failure.ignore clean package"
   step([$class: 'JUnitResultArchiver', testResults: '**/target/surefire-reports/TEST-*.xml'])
   }  
}
