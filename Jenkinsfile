pipeline {
 agent {
     node {
         label 'master'
     }
 }
stages {
    stage ('build'){
     steps{   
                sh """
                cd /home/gnaneshasgmail/pg_devops_assessment_01
                docker build -t gnanesha/nginx:test .            
                """
      }
    }
    stage ('run'){
     steps{   
                sh """
                docker run -it --rm -d -p 5050:80 --name web gnanesha/nginx:test             
                """
      }
    }
   stage ('push'){
    steps{   
               sh """
               docker login -u gnanesha -p N@tures@132
               docker push gnanesha/nginx:test
               """
     }
   }    
  }
} 
