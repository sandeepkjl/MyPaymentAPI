pipeline {
    agent any



stages{
        stage('init'){
            steps{
                echo 'initialization...'
            }
        }
		
        stage('Build'){
            
            steps {
                bat 'mvn clean package'              
            }
        }
        stage('upload to artifactory'){
            steps{
               bat 'docker build . -t payment'
            }
        }
       
	   stage('push image to docker hub'){
            
            steps {
                bat 'docker login   -u sk6785 -p Sandeep@123'
				bat 'docker tag payment sk6785/payment:3.0'
				bat 'docker push  sk6785/payment:3.0'
				
            }
        }
      

}
}