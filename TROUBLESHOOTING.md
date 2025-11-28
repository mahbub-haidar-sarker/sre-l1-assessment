01. Changed the /healthz endpoint in main.py from returning HTTP 500 to HTTP 200 OK.
02. Reconfigured the readiness probe to correctly target port 8080.
03. Built the Docker image for the Flask application.
04. Set the working directory inside the Docker image to /app.


Documentation

mkdir -p sre-l1-assessment/app
mkdir -p sre-l1-assessment/k8s
cd sre-l1-assessment

touch app/main.py
#return jsonify({"status": "ok"}), 200 # Update This Line
touch app/requirements.txt
touch Dockerfile
#WORKDIR /app # Update This Line
#EXPOSE 8080  # Update This Line
touch k8s/deployment.yaml
#- containerPort: 8080 # Update This Line
#port: 8080 # Update This Line
touch k8s/service.yaml
touch logs.txt
touch TROUBLESHOOTING.md

echo "__pycache__/" >> .gitignore
echo "*.log" >> .gitignore

git init
git add .
git commit -m "Final Update"
git remote add origin ssh://github.com/mahbub-haidar-sarker/sre-l1-assessment.git
git branch -M main
git push -u origin main
git remote add origin git@github.com:mahbub-haidar-sarker/sre-l1-assessment.git

