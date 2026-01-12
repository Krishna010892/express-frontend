GitHub repo link for flask-backend - https://github.com/Krishna010892/flask-backend

Below are the steps.

Step 1: EC2 Setup
Launched an Ubuntu 24.04 EC2 instance.

Installed required dependencies:
sudo apt update
sudo apt install python3-pip python3-venv nodejs npm git

Configured security groups:
SSH (22)
Flask (5000)
Express (3000)
Jenkins (8080)

Step 2: Application Deployment
Flask backend:
git clone <flask-backend-repo>
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
pm2 start app.py --name flask-app

Express frontend:
git clone <express-frontend-repo>
npm install
pm2 start app.js --name express-app

Step 3: Jenkins CI/CD Pipeline
Installed Jenkins on EC2.
Installed plugins: Git, NodeJS, Python, Pipeline.
Created Freestyle projects:
flask-pipeline (pulls Flask repo, installs dependencies, restarts Flask app)
express-pipeline (pulls Express repo, installs dependencies, restarts Express app)
Configured GitHub webhooks for both pipelines to trigger on push events.

Step 4: Testing the CI/CD Pipeline
Verified that pushing new code automatically triggers Jenkins build and redeploys the apps.
Optional Enhancements
Use Jenkins environment variables for secrets (like API keys or DB credentials).
Add automated tests stages for each pipeline.

For SS, kindly find "SS FOR JENKINS CI CD PIPELINE" excel mention on same repo.

