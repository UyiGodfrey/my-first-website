<h1>Steps involved in creating this repository</h1>

## Step 1: Create Your GitHub Repository
- Go to github.com and log in.
- Click the + icon (top right) and select New repository.
- Name it (e.g., my-first-project).
- Leave Initialize this repository with README unchecked (we’ll d>
- Click Create repository.

## Step 2: Set Up Git Locally and Make Your First Commit
- Open Git Bash on your computer:
- mkdir my-first-project
- cd my-first-project
- echo "# My First Project" > README.md
- git init
- git add README.md
- git commit -m "Initial commit with README"

## Step 3: Link Your Local Repo to GitHub and Push
- Copy the HTTPS URL of your GitHub repo (something like [https://github.com/youru>](https://github.com/youru>)
- git remote add origin [https://github.com/yourusername/my-first-project.git](https://github.com/yourusername/my-first-project.git)
- git branch -M main
- git push -u origin maintenance

## Step 4: Launch an EC2 Instance and Connect via SSH
- Go to AWS Console > EC2 > Launch Instance
- Choose Ubuntu Server (latest LTS)
- Download your .pem key file
- Set security group to allow ports 22 (SSH) and 80 (HTTP)
- Launch the instance

## Then connect using Git Bash:
- ssh -i /path/to/your-key.pem ubuntu\@your-ec2-public-ip

## Step 5: Install Apache and Deploy a Simple HTML Site
- sudo apt update
- sudo apt install apache2 -y
- sudo systemctl start apache2
- sudo systemctl enable apache2
- cd /var/www/html
- sudo rm index.html
- sudo nano index.html
- Save and exit (Ctrl + O, then Enter, then Ctrl + X).

## Step 6: View Your Website
- Open your browser and go to:
- [http://your-ec2-public-ip](http://your-ec2-public-ip)


