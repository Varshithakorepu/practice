pipeline{
    agent win
    stages{
        stage('Build and Run'){
            steps{
                bat """
                if exist out rmdir /s /q out
                mkdir out
                javac -d out src//Hello.java
                java -cp out Hello
                echo Build_OK > artifact.txt
                """
                }
            }
        }
    post{
        always{
            archiveArtifacts artifacts :'artifact.txt, out/**'
        }
    }
}
