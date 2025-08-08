Setting hostname - sudo hostnamectl set-hostname <new_hostname>
Github push repo to github

Yum install git -y
ssh-keygen
Cd .ssh
Copy the public key, now add this in github
Cd data/
git init
git add .
git commit -m "Initial commit"
git remote add origin git@github.com:arkaprovolti/first-app.git
git remote -v
git push  origin master



Github: cloning same repo and pushing it to same repo;
git clone git@github.com:arkaprovolti/first-app.git
cat > sds.txt
sdaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa yeyyy
git add .
 git commit -m "Initial commit"
git push  origin main


Github- cloning a different repo and pushing it to my repo
git clone git@github.com:sanjayguruji/java-code-with-maven.git
Now go inside /java-code-with-maven directory cloned
git remote -v
git remote set-url origin git@github.com:arkaprovolti/java-maven-arka-2.git
Git push origin main

Jenkins
15 gb gp2 instance
 yum update -y
Google search installing jenkins on aws
sudo wget -O /etc/yum.repos.d/jenkins.repo \
https://pkg.jenkins.io/redhat-stable/jenkins.repo
Yum repolist all
sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io-2023.key
Instance -> security groups -> select your one -> edit inbound rules ->add custom tcp -> port range 8080 -> 0.0.0.0/0
Now copy public ip : 8080
sudo yum install java-17-amazon-corretto -y
Sudo yum install jenkins -y
Systemctl enable jenkins
Systemctl start jenkins
Open public ip of server
Paste vim  /var/lib/jenkins/secrets/initialAdminPassword and unlock jenkins
Now gotta increase size of temp
sudo mount -o remount, size=2G /tmp
df -h
vim /etc/fstab
tmpfs /tmp tmpfs defaults,noatime,mode=1777,size=2G
Sudo mount -a
Systemctl daemon-reload
Reboot instance
in case if ec2 instance is shutdown, jenkins node will go slow. To solve this, go to
Cd /var/lib/jenkins -> jenkins.model…….xml -> open it in vim -> we got an ip address, replace it with port ip.
Now we gotta integrate jenkins server with our github repo.
Add webhooks in our github repo
Payload url should look like http://51.20.118.218:8080/github-webhook/
You gotta get secret, for this go to jenkins -> security -> create api token, githooks -> allow on agents.
Now we will make a pipeline in jenkins -> new item -> freestyle ->ok
Go to configure, of the created pipeline, and paste repo url in htpps
yum install git
Now build pipeline

Tomcat server setup
8080 port inbound rules
Copy core tar.gz
 wget https://dlcdn.apache.org/tomcat/tomcat-9/v9.0.108/bin/apache-tomcat-9.0.108.tar.gz
tar xvzf apache-tomcat-9.0.108.tar.gz
rm -rf apache-tomcat-9.0.108.tar.gz
 cd  apache-tomcat-9.0.108
yum install java -y
Cd bin
ls
Google Step by Step guide to install Apache Tomcat on Amazon Linux by  Medium
chmod +x startup.sh
chmod +x shutdown.sh
Cd conf
find -name context.xml
