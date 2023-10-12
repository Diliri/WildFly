pipeline {
    agent { 
        label "ubuntu-slave" 
    }

    tools {
        // Install the Maven version configured as "M3" and add it to the path.
        maven "M3"
    }

    stages {
        stage('Build') {
            steps {
                sh " rm -rf WildFly-Servlet-Example"
                
                // Get some code from a GitHub repository
                sh "git clone https://github.com/YegorMaksymchuk/WildFly-Servlet-Example.git"

                // Run Maven on a Unix agent.
                sh "cd WildFly-Servlet-Example/ && mvn clean install"

            }
    
    post { 
        always { 
            echo 'I will always say Hello again!'
        }
    }
        }
    }
}
