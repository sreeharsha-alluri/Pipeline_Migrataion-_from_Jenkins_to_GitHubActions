# Pipeline_Migrataion_from_Jenkins_to_GitHubActions
# Install Jenkins
sudo apt update -y && sudo apt install default-jdk -y && sudo apt install default-jre -y
wget -q -O - https://pkg.jenkins.io/debian-stable/jenkins.io.key | sudo apt-key add -
sudo sh -c 'echo deb http://pkg.jenkins.io/debian-stable binary/ > /etc/apt/sources.list.d/jenkins.list'
sudo apt update -y
sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys 5BA31D57EF5975CA
sudo apt update -y
sudo apt install jenkins -y
sudo systemctl status jenkins
sudo cat /var/lib/jenkins/secrets/initialAdminPassword

# Install Docker
curl https://get.docker.com/ | sudo bash
sudo systemctl status docker

# Install GitHub CLI
sudo apt-add-repository https://cli.github.com/packages
sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-key 23F3D4EA75716059
sudo apt update -y
sudo apt install gh
gh --version

# Authenticate with GitHub
gh auth login

#Install the GitHub Actions Importer CLI extension
gh extension install github/gh-actions-importer

#Verify that the extension is installed
gh actions-importer -h
gh actions-importer configure

