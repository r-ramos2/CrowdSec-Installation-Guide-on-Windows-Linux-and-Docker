# CrowdSec Installation Guide on Windows, Linux, and Docker

## Table of Contents
1. [Installation on Windows or Linux](#installation-on-windows-or-linux)
2. [Installation on a Docker Container](#installation-on-a-docker-container)
3. [Best Practices for Installing CrowdSec](#best-practices-for-installing-crowdsec)
4. [Resources](#resources)

---

## Installation on Windows or Linux

Follow the steps below to install and configure CrowdSec on your Windows or Linux system.

### Steps:

1. **Visit CrowdSec Website**  
   Go to [crowdsec.net](https://www.crowdsec.net) and sign up for an account.
   
2. **Download and Install CrowdSec**  
   From the website, download the appropriate installation file for your system (Windows or Linux). Follow the installation instructions to complete the setup.

3. **Enroll Your Instance**  
   After installation, return to your CrowdSec account on the website and locate the **Enroll your instance** section. Copy the provided enroll command.

4. **Run Enroll Command**  
   Open your terminal (without using sudo), and enter the copied enroll command to connect your system to CrowdSec.

5. **Accept Enroll Request**  
   Go back to the CrowdSec dashboard and accept the enroll request to link your machine.

6. **Verify Installation**  
   After enrolling, verify the installation by running the following command in your terminal:
   ```bash
   cscli alerts list
   ```
   This will list any detected alerts, confirming that CrowdSec is successfully installed and working.

---

## Installation on a Docker Container

Running CrowdSec in a Docker container provides a lightweight and isolated environment for securing your system. Follow these steps to install CrowdSec in Docker.

### Prerequisites:

- Make sure Docker is installed and running on your machine. If not, download Docker from [here](https://www.docker.com/products/docker-desktop).

### Steps:

1. **Install Docker**  
   If Docker is not yet installed, visit [Docker’s official website](https://www.docker.com/get-started) to download and install it.

2. **Search for CrowdSec Image**  
   In the Docker Desktop or CLI, search for the **CrowdSec** image by running:
   ```bash
   docker search crowdsec
   ```

3. **Pull and Run the CrowdSec Image**  
   Find the **crowdsecurity/crowdsec** image, and pull it by running:
   ```bash
   docker pull crowdsecurity/crowdsec
   ```

4. **Run the Container**  
   To create and run the CrowdSec container, use the following command in Docker CLI:
   ```bash
   docker run -d --name CrowdSec crowdsecurity/crowdsec
   ```

5. **Enroll the Docker Instance**  
   Go to [crowdsec.net](https://www.crowdsec.net) and find the **Enroll your CrowdSec Instance!** section. Copy the provided command for Debian/Ubuntu.

6. **Open Docker Terminal**  
   Open the terminal in Docker and enter the enroll command (without using sudo).

7. **Accept Enroll Request**  
   In the CrowdSec dashboard, accept the enroll request to link your Docker container instance.

8. **Verify Installation**  
   Verify the setup by running the following command in Docker's terminal:
   ```bash
   docker exec CrowdSec cscli alerts list
   ```
   This will confirm that alerts are being logged and that CrowdSec is functioning within the Docker container.

---

## Best Practices for Installing CrowdSec

- **Always Verify Enrollment**: After installing CrowdSec, ensure your instance is properly enrolled and connected to the CrowdSec network to receive updates and community-driven blocklists.
- **Use Docker for Isolation**: Running CrowdSec in Docker provides an isolated environment, making it easier to manage and maintain without interfering with your host system.
- **Review Alerts Regularly**: Use the `cscli alerts list` command to review suspicious behavior and adjust your security policies accordingly.

---

## Resources

- [CrowdSec Documentation](https://docs.crowdsec.net/docs/intro)
- [Docker Hub: CrowdSec Image](https://hub.docker.com/r/crowdsecurity/crowdsec)
