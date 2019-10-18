pipeline {

    agent any



    stages {

        stage ('Compile Stage') {



            steps 

              {

                   bat label: '', script: 'mvn compile'

                }

            }

        
        stage ('Testing Stage') {



            steps 

                 {

                    bat label: '', script: 'mvn test'

                }

            

        }





        stage ('Package Stage') {

            steps 

                {

                    bat label: '', script: 'mvn package'

                }

            }

        stage ('Deploy Stage') {
            
            steps
            {
                deploy adapters: [tomcat9(credentialsId: '7b10c527-3e2a-4619-9e4f-b5d406660497', path: '', url: 'http://localhost:8095/manager/html')], contextPath: 'my-third-mvn-project-1.0-SNAPSHOT', war: '**/*.war'
                bat label: '', script: 'mvn deploy'
    }
        }

}
}
