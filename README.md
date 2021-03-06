# Docker Dradis Recon Launcher

### Purpose
For managing multiple instances of single user Dradis Community Edition to manage individual recon workflow across multiple projects.

### General Use
Allow a user to easily configure `HOST_PORT`, `DATA_VOLUME` and `CONTAINER_NAME` via `.env` file and use a few simple scripts to spin up and down multiple different recon environments as they work across projects.

### Pre-requisites
* Docker
* Mac/Linux

### Install and Setup
1. Clone Repo: `git clone https://github.com/jaywon/dradis-docker-recon-launcher your-project-name`
1. Change into project directory: `cd your-project-name`
1. Copy `.env` template: `cp .env.example .env`
1. Edit `.env` to name container based on project and change port and data directory(if needed)
1. Start environment `./start-dradis`
1. Browser will launch with configured local address

### Stop Environment
1. Stop environment `./stop-dradis`

**NOTE:** The next time you want to run the project simply run `./start-dradis` again and it will detect if you had a previously created container and use it, or create a new one if your container has been destroyed.

**NOTE:** Using a mounted volume and local data directory to the project your recon work stays safe and portable even if your container is destroyed.

**NOTE:** The first time you create a project it will redirect you to `/login` and prompt you to set a password and then redirect you to a login page where username is `admin` and password is the password you set.

Thanks to `ikuturso` for their docker image that includes the pre-installed Dradis methodologies templates from this image: https://hub.docker.com/r/ikuturso/dradis/
