# Step 1:

# Go to EC2 console and Create an EC2 instance , t2.micro and check running status


![Screenshot (327)](https://github.com/manikantaraju427/github-webhook/assets/125948783/11777d05-4d29-4dd5-9584-a24942254bcb)


Connect to the EC2 instance using https


![WhatsApp Image 2023-10-25 at 09 51 22](https://github.com/manikantaraju427/github-webhook/assets/125948783/d62d4886-9165-405d-8f6b-07f9a3382290)


# Step 2:

# Install jenkins on AWS EC2 Ubuntu instance

1: Install Java

Jenkins requires the Java Runtime Environment (JRE).


$sudo apt update

$sudo apt install fontconfig openjdk-17-jre

verified java version

$java -version


![WhatsApp Image 2023-10-25 at 10 12 18](https://github.com/manikantaraju427/github-webhook/assets/125948783/940c5a28-b285-4db1-9914-6cb5757e05a6)


2: Install Jenkins

Update the system repository

$sudo apt-get update


![WhatsApp Image 2023-10-25 at 10 23 29](https://github.com/manikantaraju427/github-webhook/assets/125948783/c0c2792b-9b1a-4da3-afa3-58e217ac6147)


for Debian/Ubuntu

$sudo apt-get install jenkins

To check if Jenkins is installed and running, run the following command:


![Screenshot (331)](https://github.com/manikantaraju427/github-webhook/assets/125948783/2630eee4-95ed-4f9d-bcf1-e41d563c97ac)


# Step 3: Install Docker on EC2 instance

Install docker using below command:

$sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin


![Screenshot (332)](https://github.com/manikantaraju427/github-webhook/assets/125948783/320337d0-4fc0-4fa5-8959-cc1ec7b76a6e)


check docker is installed and running using command:

$sudo systemctl status docker


![WhatsApp Image 2023-10-25 at 11 11 07](https://github.com/manikantaraju427/github-webhook/assets/125948783/e7d8ab5f-238d-4e2d-adbf-a5935109cf05)


# Add user to the docker group:

$sudo usermod -a -G docker $USER

(This command adds your current user to the docker group, which grants permission to access the Docker socket.)

# Add the Jenkins user to the docker group:

$sudo usermod -a -G docker jenkins

# Setup security groups


![Screenshot (334)](https://github.com/manikantaraju427/github-webhook/assets/125948783/4b57d12b-b14b-4960-ab42-9ba1980d197e)






















