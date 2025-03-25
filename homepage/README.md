# Homepage Setup

This folder contains the configuration to run the [Homepage dashboard](https://github.com/gethomepage/homepage) using Docker Compose, following clean naming conventions.

---

## 📂 Folder Structure:

```
~/Devl/docker/homepage/
├── compose.yaml
├── .env
└── README.md
```

---

## 🌱 Environment Variables:

Defined in `.env`:

| Variable       | Default | Description            |
|----------------|---------|------------------------|
| `HOMEPAGE_PORT`| 3001    | External access port   |

---

## 🚀 Setup Instructions:

### 1️⃣ Create Directory:

```bash
mkdir -p ~/Devl/docker/homepage
cd ~/Devl/docker/homepage
```

---

### 2️⃣ Create `.env` File:

```bash
nano .env
```

Example:

```env
HOMEPAGE_PORT=3001
```

---

### 3️⃣ Create `compose.yaml` File:

```bash
nano compose.yaml
```

(See provided file content.)

---

### 4️⃣ Start Homepage:

```bash
docker compose -f compose.yaml up -d
```

---

### 5️⃣ Access Homepage UI:

```
http://localhost:3001
```

---

### 6️⃣ Verify:

```bash
docker ps
docker volume ls
docker network ls
```

You should see:

- **Volume:** `homepage_data`
- **Network:** `homepage_network`

---

### 7️⃣ Stop (Optional):

```bash
docker compose -f compose.yaml down
```

---

## ✅ Quick Commands Summary:

```bash
cd ~/Devl/docker/homepage
docker compose -f compose.yaml down
docker network prune
docker volume ls
docker network ls
docker compose -f compose.yaml up -d
http://localhost:3001
```

---

## 🔮 Optional Next Step:

- Add `homepage.local` → `127.0.0.1` in Pi-hole DNS
- Create a proxy host in Nginx Proxy Manager to point to `homepage:3001`
