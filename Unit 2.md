# Lab Workshop – Unit II (Forenoon Session)
### Jenkins Setup & Basics

This session reinforces forenoon theory: CI/CD fundamentals, Jenkins overview, architecture, and installation.
Reference - https://www.jenkins.io/doc/tutorials/build-a-java-app-with-maven/

---

## Step 1: Verify CI/CD Setup Tools
Ensure **Git**, **Docker**, and **Docker Compose** are installed:
  ```bash
  git --version
  docker --version
  docker compose version
  ```

---

## Step 2: Download Jenkins Tutorial Repo & Start Jenkins

1. Clone the Jenkins quickstart tutorials repository:

   ```bash
   git clone https://github.com/jenkins-docs/quickstart-tutorials.git
   cd quickstart-tutorials
   ```

2. Start Jenkins with the Maven profile:

   ```bash
   docker compose --profile maven up -d
   ```

3. Verify containers are running:

   ```bash
   docker compose ps
   ```

---

## Step 3: Access Jenkins

1. Open Jenkins in your browser: [http://localhost:8080](http://localhost:8080)
2. Retrieve the initial admin password:

   ```bash
   docker exec jenkins-blueocean cat /var/jenkins_home/secrets/initialAdminPassword
   ```
3. Paste the password into the setup wizard.
4. Install **Suggested Plugins**.
5. Create your first **Admin User**.

---

## Step 4: Explore Jenkins Dashboard & Architecture

* Identify **Controller (Master)** → manages jobs, plugins, and scheduling.
* Navigate to **Manage Jenkins → Nodes and Clouds** to understand how build agents connect.
* Note: In this Docker setup, Jenkins runs as a single-node (controller = agent).

---

## Step 5: Configure Basic Plugins

1. Navigate to **Manage Jenkins → Plugins → Available Plugins**.
2. Install:

   * **Git plugin** (for version control integration)
   * **Pipeline plugin** (for later pipeline labs)
   * **Blue Ocean** (modern UI for pipelines)

---

✅ At the end of this forenoon lab you will have:

* Jenkins installed and running in Docker
* Admin user configured
* Key plugins installed
* Familiarity with Jenkins architecture and dashboard
