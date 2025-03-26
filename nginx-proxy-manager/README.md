# Nginx Proxy Manager Setup

This folder contains the configuration to run **Nginx Proxy Manager** using Docker Compose, following clean naming conventions.

---

## 📂 Folder Structure:

```
~/Devl/docker/nginx-proxy-manager/
├── docker-compose.yml
├── .env
└── README.md
```

---

## 🌱 Environment Variables:

Defined in `.env`:

| Variable             | Default         | Description                              |
|---------------------|-----------------|------------------------------------------|
| `NPM_HTTP_PORT`      | 8081            | HTTP port                                |
| `NPM_HTTPS_PORT`     | 4443            | HTTPS port                               |
| `NPM_ADMIN_EMAIL`    | admin@example.com | Default admin email                     |
| `NPM_ADMIN_PASSWORD` | changeme        | Default admin password                   |

---

## 🚀 Full Setup Instructions:

### 1️⃣ Create Directory:

```bash
mkdir -p ~/Devl/docker/nginx-proxy-manager
cd ~/Devl/docker/nginx-proxy-manager
```

---

### 2️⃣ Create `.env` File:

```bash
nano .env
```

Example:

```env
NPM_HTTP_PORT=8081
NPM_HTTPS_PORT=4443
NPM_ADMIN_EMAIL=admin@example.com
NPM_ADMIN_PASSWORD=changeme
```

Change email/password as needed.

---

### 3️⃣ Create `docker-compose.yml` File:

```bash
nano docker-compose.yml
```

(See provided file content.)

---

### 4️⃣ Start Nginx Proxy Manager:

```bash
docker compose up -d
```

---

### 5️⃣ Access Web UI:

```
http://localhost:81
```

Login:

- **Email:** admin@example.com
- **Password:** changeme

Change credentials after first login!

---

### 6️⃣ Verify:

```bash
docker ps
docker volume ls
docker network ls
```

You should see:

- **Volumes:** `nginx_proxy_manager_data`, `nginx_proxy_manager_letsencrypt`
- **Network:** `nginx_proxy_manager_network`

---

### 7️⃣ Stop (Optional):

```bash
docker compose down
```

---

## ✅ Quick Commands Summary:

```bash
cd ~/Devl/docker/nginx-proxy-manager
docker compose down
docker network prune
docker volume ls
docker network ls
docker compose up -d
http://localhost:81
```

---

## 🔮 Next Steps:

- Use NPM to reverse proxy apps like Hoarder, Portainer, etc.
