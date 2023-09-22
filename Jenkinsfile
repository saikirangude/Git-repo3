pipeline {
        agent any

    stages {

        stage ("Getting Souce Code From Git") {
            steps {
                git 'https://github.com/saikirangude/Git-repo3.git'
            }
        }
//         stage ("SonarQube analysis") {
//             steps {
//                 withSonarQubeEnv('SonarQube_Scanner') {
//                     sh 'mvn clean sonar:sonar'
//                 }
//             }
// 		}
			
        stage ("Compiling The Source Code") {
            steps {
                sh 'mvn compile'
            }
        }

        stage ("Testing The Source Code") {
            steps {
                sh 'mvn test'
            }
        }

        stage ("Generating Artifact") {
            steps {
                sh 'mvn package'
            }
	}
	    
// 	stage ("Building docker image and launching container") {
//             steps {
// 		 sshPublisher(publishers: [sshPublisherDesc(configName: 'Docker-host', transfers: [sshTransfer(cleanRemote: false, excludes: '', execCommand: 'sudo docker build -t saitomcat:1.0 /dockerfiles/dockerfile; sudo docker login; sudo docker tag saitomcat:1.0 saikirangude/dockerfiles:1.0; sudo docker push saikirangude/dockerfiles:1.0; sudo docker run -d -p 8080:8080 saikirangude/dockerfiles:1.0 --name=tomcat-container', execTimeout: 120000, flatten: false, makeEmptyDirs: false, noDefaultExcludes: false, patternSeparator: '[, ]+', remoteDirectory: '', remoteDirectorySDF: false, removePrefix: '/jenkins_home/workspace/Tasks/Tasks-1/Jenkins_Pipeline_2/target/', sourceFiles: '/jenkins_home/workspace/Tasks/Tasks-1/Jenkins_Pipeline_2/target/trucks.war')], usePromotionTimestamp: false, useWorkspaceInPromotion: false, verbose: false)])
// 	    }
// 	}
    }      
}
