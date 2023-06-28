pipeline
{
    agent any 
    stages
    {
        stage('ContDownload')
        {
            steps
            {
               git 'https://github.com/srimanvitha/mavenPipeline.git'

 
            }
            
        }
        stage('ContBuild')
        {
            steps
            {
               sh 'mvn package'
            }
            
        }
        stage('ContDeploy')
        {
            steps
            {
               deploy adapters: [tomcat9(credentialsId: '123d5bc3-01e6-456e-a2cb-70c5b681f302', path: '', url: 'http://172.31.42.0:8080')], contextPath: 'testapp', war: '**/*.war'
            }
            
        }
        stage('ContTesting')
        {
            steps
            {
                git 'https://github.com/intelliqittrainings/FunctionalTesting.git'
               sh 'java -jar /home/ubuntu/.jenkins/workspace/DeclarativePipeline/testing.jar ' 
            }
        }
        stage('ContDelivery')
        {
            steps
            {
                input message: 'Need approval from delivery Manager!', submitter: 'sri'
                deploy adapters: [tomcat9(credentialsId: '123d5bc3-01e6-456e-a2cb-70c5b681f302', path: '', url: 'http://172.31.45.224:8080')], contextPath: 'myprodapp', war: '**/*.war'
            }
        }
       
        
    }
}



    



            

























       

    




 


 


        
       
    
    
    
    
    
    
    

