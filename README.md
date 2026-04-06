# Demo Spring Boot Microservice with GitHub Actions CI/CD and AWS EC2

This project is a simple Spring Boot microservice designed for learning and experimentation with modern DevOps practices. The main focus is on understanding how to set up a CI/CD pipeline using GitHub Actions and deploy a Java application to AWS EC2.

## What I Learned

- **Spring Boot Microservice Development:**
  - Built a basic REST API using Spring Boot.
  - Understood the structure of a typical Java microservice project.

- **CI/CD with GitHub Actions:**
  - Created a GitHub Actions workflow to automate build, test, and Docker image creation.
  - Learned how to trigger workflows on code pushes and pull requests.
  - Explored best practices for automating software delivery.

- **AWS EC2 Deployment:**
  - Deployed the Dockerized application to an AWS EC2 instance.
  - Managed EC2 setup, security groups, and SSH access.
  - Understood the basics of cloud deployment and infrastructure.

- **End-to-End Automation:**
  - Connected code changes to automatic deployment, reducing manual steps.
  - Saw the value of continuous integration and continuous delivery in real-world projects.

## Setup Steps

1. **Clone the Repository**
   ```sh
   git clone <your-repo-url>
   cd demo
   ```

2. **Configure AWS EC2**
   - Launch an EC2 instance (Amazon Linux or Ubuntu recommended).
   - Open required ports (e.g., 8080 for the app, 22 for SSH).
   - Install Docker on the EC2 instance.
   - Set up SSH keys for secure access.

3. **Set up GitHub Secrets**
   - Add your EC2 server's IP, SSH username, and private key as GitHub repository secrets.
   - Example secrets:
     - `EC2_HOST`
     - `EC2_USER`
     - `EC2_SSH_KEY`

4. **GitHub Actions Workflow**
   - The workflow file is located at `.github/workflows/docker-image.yml`.
   - On every push, the workflow will:
     - Build the project with Maven
     - Build a Docker image
     - SSH into the EC2 instance and deploy the new image

5. **Run the Application**
   - After a successful deployment, access the app at `http://<EC2_HOST>:8080/`

## Notes

- **Learning Purpose:** This project is for educational use only. It is not production-ready and may lack advanced security or scalability features.
- **Customization:** Feel free to modify the code, workflow, or deployment steps to fit your learning goals.
- **References:**
  - [Spring Boot Documentation](https://spring.io/projects/spring-boot)
  - [GitHub Actions Documentation](https://docs.github.com/en/actions)
  - [AWS EC2 Documentation](https://docs.aws.amazon.com/ec2/)

---

*Created as a hands-on exercise to learn about microservices, CI/CD, and cloud deployment.*
