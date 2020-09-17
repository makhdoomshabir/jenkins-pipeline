pipeline{
        agent any
        stages{
             stage('Git clone'){
                steps{
                    sh "git clone https://gitlab.com/qacdevops/chaperootodo_client.git"
                }
            }
             stage('docker and docker-compose install'){
                steps{
                    sh '''
                    curl https://get.docker.com | sudo bash
                    sudo curl -L "https://github.com/docker/compose/releases/download/1.27.3/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
                    sudo chmod +x /usr/local/bin/docker-compose
                    '''
                }
            }
             stage('deploy'){
                steps{
                    sh "sudo docker-compose up -d"
                }
            }     
                
        }    
}
