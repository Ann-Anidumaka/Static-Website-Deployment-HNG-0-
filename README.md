# Static-Website-Deployment-HNG-0-Rocket

## Project Overview
Deployed a static website using NGINX on AWS EC2 as part of the HNG Internship DevOps track. The website includes HTML, CSS, and JavaScript components showcasing my skills, along with personal information such as Name, username, and email. The project meets all specified requirements, including successful deployment on a AWS and correct configuration of NGINX to serve website content.

### Features

- Responsive design using Bootstrap
- Interactive elements with JavaScript
- required content

### Deployment Instructions

To deploy this website:

1. **Cloud Platform**: AWS EC2
2. **Web Server**: NGINX
3. ### Steps

### Step 1: Launch an AWS EC2 Instance

1. **Log into AWS Console**:
   - Navigate to AWS Management Console and log in.

2. **Launch EC2 Instance**:
   - Choose EC2 from the services menu.
   - Click on "Launch Instance".
   - Select an Amazon Machine Image (AMI), configure instance details, add storage, configure security groups (allow HTTP), and launch the instance.

3. **Connect to EC2 Instance**:
   - Use EC2 Instance Connect or SSH to connect to your instance.

### Step 2: Install NGINX

1. **Update Packages**:
   ```bash
   sudo yum update -y
   
2. **Install NGINX**:
   ```bash
   sudo yum install nginx -y

3. **Start NGINIX**:
   ```bash
   sudo systemctl start nginx

### Step 3: Deploy Static Website

1. **Copy HTML File**:
   - Navigate to the directory where NGINX serves its web content:
     ```bash
     cd /usr/share/nginx/html
     ```

2. **Paste HTML Content**:
   - Open the index.html file
     ```bash
     sudo vim index.html
     ```
     Paste the HTML content of your website into the editor.

3. **Save and Exit**:
   - Save the changes and exit the editor:

4. **Verify NGINX Configuration**:
   - Check NGINX configuration for any syntax errors:
     ```bash
     sudo nginx -t
     ```

### Step 4: Configure NGINX 
   
1. **Modify NGINX Configuration**:
   ```bash
   sudo vim /etc/nginx/conf.d/default.conf

2. **replace thr contents with**:
   ```bash
   server {
    listen 80;
    server_name your-domain.com;

    root /usr/share/nginx/html;
    index index.html index.htm;

    location / {
        try_files $uri $uri/ =404;
    }
   }

4.  **Test and restart NGINX Configuration**:
   ```bash
   sudo nginx -t
   sudo systemctl restart nginx




   
### Technologies Used

- NGINX
- AWS EC2
