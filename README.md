 Simple Jenkins Pipeline for CI/CD
Prerequisites
**Red Hat system (any version that supports Jenkins installation).
Jenkins installed and running.
Docker installed and configured on Jenkins server.
A GitHub repository with the application code.**
**Install Jenkins**
1.sudo dnf update -y
2.sudo dnf install java-11-openjdk-devel -y
3.sudo wget -O /etc/yum.repos.d/jenkins.repo https://pkg.jenkins.io/redhat/jenkins.repo
sudo rpm --import https://pkg.jenkins.io/jenkins.io.key
4.sudo dnf install jenkins -y
5.sudo systemctl start jenkins
sudo systemctl enable jenkins
6.sudo cat /var/lib/jenkins/secrets/initialAdminPassword
Create a New Jenkins Job
a.Open Jenkins on your browser and log in with your credentials.
**Create a New Pipeline Job**
From the Jenkins dashboard, click on New Item.
Enter the job name (e.g., MyApp-CI-CD).
Select Pipeline as the project type and click OK.
**Configure the Pipeline**
**Steps to Add the Jenkinsfile to Your Repository**
1.git add Jenkinsfile
2.git commit -m "Add Jenkinsfile for CI/CD pipeline"
3.git push origin main
**Docker Setup**
1.sudo dnf install -y yum-utils device-mapper-persistent-data lvm2
sudo dnf config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
sudo dnf install docker-ce docker-ce-cli containerd.io -y
2.sudo systemctl start docker
sudo systemctl enable docker
3.sudo usermod -aG docker jenkins
sudo systemctl restart jenkins
4.sudo docker --version
Test the Pipeline
Conclusion
You have successfully set up a Jenkins CI/CD pipeline on a Red Hat system to automate the build, test, and deployment of your application using Docker. This pipeline will automatically trigger whenever you push changes to your Git repository, ensuring seamless integration and delivery.



