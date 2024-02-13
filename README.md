# Pipeline_Migration_from_Jenkins_to_GitHubActions <br>
# Reference Link :
https://docs.github.com/en/actions/migrating-to-github-actions/automated-migrations/migrating-from-jenkins-with-github-actions-importer

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
Install the Paginated Builds plugin in Jenkins GUI <br>

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
gh actions-importer update <br>
gh actions-importer audit jenkins --output-dir tmp/audit <br>
gh actions-importer forecast jenkins --output-dir tmp/forecast <br>

# Syntax <br>
gh actions-importer dry-run jenkins --source-url my-jenkins-project --output-dir tmp/dry-run <br>

# Example with job named as Pipeline_1 <br>
gh actions-importer dry-run jenkins --source-url http://54.92.219.56:8080/job/Pipeline_1/ --output-dir tmp/dry-run <br>
# Syantx <br>
gh actions-importer migrate jenkins --target-url https://github.com/:owner/:repo --output-dir tmp/migrate --source-url my-jenkins-project <br>
# Example with job named as Pipeline_1 <br>
gh actions-importer migrate jenkins --target-url https://github.com/sreeharsha-alluri/Pipeline_Migrataion- _from_Jenkins_to_GitHubActions.git --output-dir tmp/migrate --source-url http://54.92.219.56:8080/job/Pipeline_1/ <br>
# Example with job named as Test <br>
gh actions-importer dry-run jenkins --source-url http://54.92.219.56:8080/job/Test/ --output-dir tmp/dry-run <br>
gh actions-importer migrate jenkins --target-url https://github.com/sreeharsha-alluri/Pipeline_Migrataion-_from_Jenkins_to_GitHubActions.git --output-dir tmp/migrate --source-url http://54.92.219.56:8080/job/Test/ <br>




