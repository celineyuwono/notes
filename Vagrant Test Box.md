## V
 Making Vagrant Box  
mkdir training-box  
cd training-box/  
vagrant init hashicorp/bionic64  
vagrant up  
vagrant ssh  
In Vagrantfile, add this line: config.vm.network "forwarded_port", guest: 8080, host: 3007 // To test on local host, use localhost:3007  
sudo apt update && sudo apt upgrade// Installing Chef Workstation  
wget  [https://packages.chef.io/files/stable/chef-workstation/0.2.43/ubuntu/18.04/chef-workstation_0.2.43-1_amd64.deb](https://slack-redir.net/link?url=https%3A%2F%2Fpackages.chef.io%2Ffiles%2Fstable%2Fchef-workstation%2F0.2.43%2Fubuntu%2F18.04%2Fchef-workstation_0.2.43-1_amd64.deb)  
sudo dpkg -i chef-workstation_0.2.43-1_amd64.deb  
chef -v// Installing Docker  
sudo apt install docker.io  
sudo systemctl start docker && sudo systemctl enable docker  
docker --version// Installing Jenkins  
Follow this url: [https://www.digitalocean.com/community/tutorials/how-to-install-jenkins-on-ubuntu-18-04](https://slack-redir.net/link?url=https%3A%2F%2Fwww.digitalocean.com%2Fcommunity%2Ftutorials%2Fhow-to-install-jenkins-on-ubuntu-18-04)  
sudo apt install openjdk-8-jdk  
wget -q -O - [http://pkg.jenkins-ci.org/debian/jenkins-ci.org.key](https://slack-redir.net/link?url=http%3A%2F%2Fpkg.jenkins-ci.org%2Fdebian%2Fjenkins-ci.org.key) | sudo apt-key add -  
sudo sh -c 'echo deb [http://pkg.jenkins-ci.org/debian-stable](https://slack-redir.net/link?url=http%3A%2F%2Fpkg.jenkins-ci.org%2Fdebian-stable) binary/ > /etc/apt/sources.list.d/jenkins.list'  
sudo apt update  
sudo apt install jenkins  
sudo systemctl start jenkins  
sudo systemctl status jenkins  
sudo ufw allow 8080  
sudo ufw status  
sudo cat /var/lib/jenkins/secrets/initialAdminPassword// See running ports  
sudo netstat -tulpn | grep LISTEN// Installing Ansible  
sudo apt update  
sudo apt install software-properties-common  
sudo apt-add-repository --yes --update ppa:ansible/ansible  
sudo apt install ansible// Installing Kitchen with Ruby Gem  
sudo apt install ruby-full  
gem install test-kitchen
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE2NzY0NTI4OThdfQ==
-->