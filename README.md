# JiraSyncBot

# 🤖 GitHub to Jira Automation via Python & Flask

This DevOps automation project enables seamless creation of Jira tickets from GitHub issues — triggered by a simple comment: `/Jira`. Built using Python, Flask, and deployed on AWS EC2, this integration streamlines cross-platform issue tracking.

## 🚀 Project Highlights

- 🐍 Python script to create Jira tickets using Atlassian REST API
- 🌐 Flask app to expose the script as an API endpoint
- ☁️ Hosted on AWS EC2
- 🔄 GitHub Webhook triggers the API when issues are commented
- 🗯️ Comment `/Jira` on any GitHub issue to auto-create a Jira ticket

---

## 🧱 Step-by-Step Workflow

1. **🔐 Set up Jira Atlassian Account**  
   - Created a Jira account and generated an API token  
   - Reviewed the [Jira REST API documentation](https://developer.atlassian.com/cloud/jira/platform/rest/v3/intro/)  

2. **⚙️ Script Jira Ticket Creation in Python**  
   - Used `requests` to authenticate with Jira and post new tickets  
   - Accepted parameters: summary, description, reporter  

3. **🌐 Turned Script into a Flask API**  
   - Flask listens for GitHub Webhook payloads  
   - Parses GitHub issue data  

4. **🚀 Deployed Flask App on AWS EC2**  
   - Configured a Ubuntu EC2 instance  
   - Installed Python, Flask, and set up security groups  
   - Hosted app with `gunicorn` + `nginx` (production ready)

5. **🔁 Created GitHub Webhook**  
   - Points to Flask API endpoint  
   - Listens for `issue_comment` events  

6. **🧠 Added Comment Logic**  
   - If a GitHub issue comment contains `/Jira`, the webhook triggers Jira ticket creation  
   - Ensures controlled, intentional ticket syncing

---

## 🧪 Demo Example

```txt
GitHub:
  New issue: "Fix login error on mobile"
  Comment: "/Jira"

Jira:
  ✅ Ticket created: [BUG] Fix login error on mobile


🛠️ Tech Stack
Python 3.10

Flask

Jira REST API

AWS EC2

GitHub Webhooks

Gunicorn + NGINX

