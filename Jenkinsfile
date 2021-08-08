pipeline {
    agent any
	
// 	  tools
//     {
//        maven "Maven"
//     }
 stages {
      stage('checkout') {
           steps {
             
                git branch: 'master', url: 'https://github.com/yogesh93400/CI-CD-using-Docker'
             
          }
        }
// 	 stage('Execute Maven') {
//            steps {
             
//                 sh 'mvn package'             
//           }
//         }
        

  stage('Docker Build and Tag') {
           steps {
              
                bat 'docker build -t yogesh:latest .' 
                bat 'docker tag yogesh yogesh93/calculatorproject:latest'
                //sh 'docker tag samplewebapp nikhilnidhi/samplewebapp:$BUILD_NUMBER'
               
          }
        }
     
  stage('Publish image to Docker Hub') {
          
            steps {
  withCredentials([string(credentialsId: 'a84fb658-7846-485a-ba84-da5c1013832b', variable: 'dockerhub_id')]) {
    // some block

          sh  'docker push yogesh93/calculatorproject:latest'
        //  sh  'docker push nikhilnidhi/samplewebapp:$BUILD_NUMBER' 
        }
	    }}             
//           }
//         }
     
//       stage('Run Docker container on Jenkins Agent') {
             
//             steps 
// 			{
//                 sh "docker run -d -p 8003:8080 nikhilnidhi/samplewebapp"
 
//             }
//         }
//  stage('Run Docker container on remote hosts') {
             
//             steps {
//                 sh "docker -H ssh://jenkins@172.31.28.25 run -d -p 8003:8080 nikhilnidhi/samplewebapp"
 
//             }
//         }
    }
	}
    
