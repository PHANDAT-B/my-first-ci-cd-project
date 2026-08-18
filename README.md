This project demonstrates a basic CI/CD pipeline using Jenkins and Docker to build and test a Node.js and Python application

  1. Prerequisites : Ensure you installed on your Jenkins host : 

                - Docker
                - Jenkins
                - Docker pipeline plugin on Jenkins host
  2. Step 1 : Clone the repository on your Jenkins host

                  - git clone https://github.com/PHANDAT-B/my-first-ci-cd-project

     Step 2 : Configure Jenkins
     
                  - Open your Jenkins dashboard
                  - Create a new pipeline item
                  - In pipeline item, find and type "Pipeline script from SCM"
                  - Choose git and paste your repository URL
                  - Ensure the path points to the Jenkins file (Jenkinsfile)
   3. How the pipeline works

                    - Instead of manually installing dependencies, the pipelines using Jenkinsfile to set up a Docker container as a agent
                    - The pipeline pulls the Docker image to procide the neccessary runtime environment
                    - Jenkins automatically executions command inside the container ( pip install or npm install)
      
