<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Steps to Create a Repository and Deploy on EC2</title>
</head>
<body>
    <h1>Steps Involved in Creating this Repository and Deploying a Simple Website</h1>

    <h2>Step 1: Create Your GitHub Repository</h2>
    <ol>
        <li>Go to <a href="https://github.com" target="_blank">github.com</a> and log in.</li>
        <li>Click the + icon (top right) and select <strong>New repository</strong>.</li>
        <li>Name it (e.g., <em>my-first-project</em>).</li>
        <li>Leave <em>Initialize this repository with README</em> unchecked.</li>
        <li>Click <strong>Create repository</strong>.</li>
    </ol>

    <h2>Step 2: Set Up Git Locally and Make Your First Commit</h2>
    <pre>
Open Git Bash on your computer and run the following:
    
mkdir my-first-project
cd my-first-project
echo "# My First Project" > README.md
git init
git add README.md
git commit -m "Initial commit with README"
    </pre>

    <h2>Step 3: Link Your Local Repo to GitHub and Push</h2>
    <p>Copy the HTTPS URL of your GitHub repository (something like <code>https://github.com/yourusername/my-first-project.git</code>), then run:</p>
    <pre>
git remote add origin https://github.com/yourusername/my-first-project.git
git branch -M main
git push -u origin main
    </pre>

    <h2>Step 4: Launch an EC2 Instance and Connect via SSH</h2>
    <ol>
        <li>Go to AWS Console &gt; EC2 &gt; Launch Instance.</li>
        <li>Select <strong>Ubuntu Server (latest LTS)</strong>.</li>
        <li>Download your <code>.pem</code> key file.</li>
        <li>Set the security group to allow ports 22 (SSH) and 80 (HTTP).</li>
        <li>Launch the instance.</li>
    </ol>
    <p>Then connect using Git Bash:</p>
    <pre>
ssh -i /path/to/your-key.pem ubuntu@your-ec2-public-ip
    </pre>

    <h2>Step 5: Install Apache and Deploy a Simple HTML Site</h2>
    <pre>
sudo apt update
sudo apt install apache2 -y
sudo systemctl start apache2
sudo systemctl enable apache2
cd /var/www/html
sudo rm index.html
sudo nano index.html
    </pre>
    <p>Then save and exit the editor (Ctrl + O, Enter, then Ctrl + X).</p>

    <h2>Step 6: View Your Website</h2>
    <p>Open your browser and go to:</p>
    <p><strong>http://your-ec2-public-ip</strong></p>

</body>
</html>

