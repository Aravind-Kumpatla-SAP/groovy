node {  
    stage('compile') { 
        sh 'cd /var/lib/jenkins/workspace/Groovy-Test'
        sh 'rm -rf *'
        sh 'git clone https://github.com/Aravind-Kumpatla-SAP/groovy'
    }
    stage('Deploy') { 
        /* sh 'docker rm -f $(docker ps -a)' */
        /* sh 'docker network create -d mynetwork --subnet=11.12.0.0/16 --ingress --opt com.docker.network.mtu=9216 --opt encrypted=true my-ingress-network' */
        sh 'docker build -t app:latest /var/lib/jenkins/workspace/CICD-JenkinsFILE/.'
        sh 'docker run -itd --privileged --name mycontainer -v /var/lib/jenkins/workspace/CICD-JenkinsFILE/src/main/webapp/:/usr/local/tomcat/webapps/ --net bridge -p 1234:8080 app:latest'
        /* sh 'docker start mycontainer' */
        /* sh 'docker exec mycontainer /usr/local/tomcat/bin/shutdown.sh' */
        /* sh 'docker exec mycontainer /usr/local/tomcat/bin/startup.sh' */
    }    
    stage('deploy with ansible') {
        sh 'ansible-playbook myweb.yml'
        
        }
       
    }
