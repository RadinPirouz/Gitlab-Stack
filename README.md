# GitLab Docker Swarm Stack

This repository provides a Docker Swarm stack for deploying GitLab CE along with PostgreSQL, Redis, and Nginx as a reverse proxy.

## 📌 Features
- Deploys GitLab CE using Docker Swarm.
- Includes PostgreSQL for GitLab database management.
- Integrates Redis for caching.
- Uses Nginx as a reverse proxy.
- Persistent storage using Docker volumes.

## 🛠️ Prerequisites
- Docker and Docker Compose installed.
- A running Docker Swarm cluster.

## 🚀 Deployment Instructions

### 1️⃣ Clone the Repository
```sh
git clone https://github.com/your-username/gitlab-docker-swarm.git
cd gitlab-docker-swarm
```

### 2️⃣ Initialize Docker Swarm (if not already initialized)
```sh
docker swarm init
```

### 3️⃣ Deploy the Stack
```sh
docker stack deploy -c docker-stack.yml gitlab_stack
```

### 4️⃣ Access GitLab
- Open your browser and navigate to:  
  ```
  http://your_domain
  ```
- Default root password is set in `docker-stack.yml` under:
  ```
  gitlab_rails['initial_root_password']
  ```

## 🔧 Configuration

- **GitLab Data Storage**  
  - `Gitlab_Data/configs:/etc/gitlab`
  - `Gitlab_Data/data:/var/opt/gitlab`
  - `Gitlab_Data/logs:/var/log/gitlab`

- **PostgreSQL Credentials** (Defined in `docker-stack.yml`)
  - `POSTGRES_USER: gitlab`
  - `POSTGRES_PASSWORD: 123`
  - `POSTGRES_DB: gitlabhq_production`

- **Nginx Reverse Proxy Configuration**
  - Located in `Nginx/nginx.conf`

## 🗑️ Remove the Stack
To stop and remove all services:
```sh
docker stack rm gitlab_stack
```

## 📜 License
This project is open-source and available under the MIT License.

## 💡 Contributing
Feel free to submit issues or pull requests to improve this stack.

---

⭐ **Star this repo if you find it useful!**

Let me know if you want any modifications! 🚀
