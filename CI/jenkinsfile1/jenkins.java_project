node('built-in') 
{
   stage ('Continous download')
      {
    git branch: 'main', url: 'https://github.com/Surja07/Maven1.git'
      }
    stage ('continous build')
     {
        sh '''mvn package '''
     }
   stage ('Continous deployment')
    {
     'scp /var/lib/jenkins/workspace/pipeline5/hello.java ubuntu@172.31.9.223:/var/lib/tomcat10/webapps/hello.java'
     }
   stage ('continous testing')
    {
       sh 'mv /var/lib/jenkins/workspace/pipeline5/hello.java /var/lib/jenkins/workspace/pipeline5/HelloWorld.java'
    }
    stage ('Continous release')
    {
sh '''
javac /var/lib/jenkins/workspace/pipeline5/HelloWorld.java
'''
  sh '''
scp /var/lib/jenkins/workspace/pipeline5/HelloWorld.class ubuntu@172.31.12.169:/var/lib/tomcat10/webapps/
'''
    }
}     
