# Pipeline_Migrataion_from_Jenkins_to_GitHubActions <br>
# Install Jenkins <br>
sudo apt update -y && sudo apt install default-jdk -y && sudo apt install default-jre -y <br>
wget -q -O - https://pkg.jenkins.io/debian-stable/jenkins.io.key | sudo apt-key add - <br>
sudo sh -c 'echo deb http://pkg.jenkins.io/debian-stable binary/ > /etc/apt/sources.list.d/jenkins.list' <br>
sudo apt update -y <br>
sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys 5BA31D57EF5975CA <br>
sudo apt update -y <br>
sudo apt install jenkins -y <br>
sudo systemctl status jenkins <br>
sudo cat /var/lib/jenkins/secrets/initialAdminPassword <br>

# Install Docker <br>
curl https://get.docker.com/ | sudo bash <br>
sudo systemctl status docker <br>

# Install GitHub CLI <br>
sudo apt-add-repository https://cli.github.com/packages <br>
sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-key 23F3D4EA75716059 <br>
sudo apt update -y <br>
sudo apt install gh <br>
gh --version <br>

# Authenticate with GitHub <br>
gh auth login <br>

# Install the GitHub Actions Importer CLI extension <br>
gh extension install github/gh-actions-importer <br>

# Verify that the extension is installed <br>
gh actions-importer -h <br>
gh actions-importer configure <br>


