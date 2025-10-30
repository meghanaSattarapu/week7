pipeline {
    agent any
        stages
        {
            stage("Build"){
                steps{
                    echo 'Build'
                    bat 'docker build -t myapp .'
                }
            }
            stage("Run"){
                steps{
                    echo 'Run'
                    bat 'docker rm -f mycontainer || exit 0'
                    bat 'docker run -d -p 5000:5000 --name mycon myapp'
                }
            }
        }
    
        post{
            success{
                echo 'Test passed'
            }
            failure{
                echo 'Test failed'
            }
        }
    
}
