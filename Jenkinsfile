pipeline {
    
    agent any
    
    environment {
        
        HORA_DESPLIEGUE = sh(script: "date '+%A %W %Y %X'", returnStdout: true).trim()
        
    }

    stages {


        stage('Initialize Conexion') {
        
            steps {

                script {
                    
                    remote = [:]
                    remote.name = 'prueba'
                    remote.host = '172.20.255.15'
                    remote.user = 'desarrollo'
                    remote.password = '$fino1593575'
                    remote.allowAnyHosts = true
                        
                }
                
            }
        }
        
        stage('Me conecto al 15') {
            steps {
                script {
                    
                    try {
                        
                        sshCommand remote: remote, command: "ls /home/desarrollo/isaias"

                        sshCommand remote: remote, command: "mkdir /home/desarrollo/isaias/prueba-mia"
                        
                        echo "Me conecte al 15"
                        
                    } catch (Exception e) {
                        
                        echo "Error durante la conexion al 15"
                        
                    }
                    
                }
            }
        }

    }
    
}

