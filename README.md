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


# Step 4:

1.Browse instance-public-IP/8080 it will open jenkins dashboard.


![Screenshot (335)](https://github.com/manikantaraju427/github-webhook/assets/125948783/6d93f495-a391-4c65-94db-bfd23470114c)



2. We need an Administrator Password to unlock this. Go to terminal and use below command for password.


$cat /var/lib/jenkins/secrets/initialAdminPassword


![WhatsApp Image 2023-10-25 at 11 39 20](https://github.com/manikantaraju427/github-webhook/assets/125948783/f58fd91e-57c9-44ab-a49f-e5fc600e81be)

Paste above password in Administrator Password and click on Continue


3. Install suggested plugins


![WhatsApp Image 2023-10-25 at 11 42 55](https://github.com/manikantaraju427/github-webhook/assets/125948783/616df698-5389-44c9-8c26-be923d88ab41)


4. All the plugins installed.


![Screenshot (338)](https://github.com/manikantaraju427/github-webhook/assets/125948783/c03e3e7c-f4a7-428a-a4ac-a01986c99dad)


5. Create first admin user


![Screenshot (339)](https://github.com/manikantaraju427/github-webhook/assets/125948783/3a3368ea-04ac-4922-b0d1-5484106be006)


![Screenshot (340)](https://github.com/manikantaraju427/github-webhook/assets/125948783/987e9be0-2830-40bf-a226-35220bcf1d6f)


6. Jenkins setup is completed and jenkins is ready to use.


![WhatsApp Image 2023-10-25 at 11 52 46](https://github.com/manikantaraju427/github-webhook/assets/125948783/b81d056d-da7a-4083-b24f-aee301f4bd5f)


# Step 5: Create freestyle project


1) In jenkins dashboard, Click on ‘New Item’ button on the left sidebar.


![Screenshot (342)](https://github.com/manikantaraju427/github-webhook/assets/125948783/6d1e3117-dcf2-4708-a74f-7de844460d49)


2. Give your project a name and select “Freestyle project” as the project type.


![Screenshot (343)](https://github.com/manikantaraju427/github-webhook/assets/125948783/3828a4bb-a694-4d82-8115-e7a259fbc744)


3. In Configure, Add description


![Screenshot (344)](https://github.com/manikantaraju427/github-webhook/assets/125948783/721c15af-ac05-48f4-b42b-500da8f02f0f)


4. In source code management, Write your GitHub repository URL



















