# Hoarder Bookmarking App Setup

This folder contains the configuration to run **Hoarder** bookmarking app using Docker Compose, following clean naming conventions and official recommended `.env` structure.

---

## 📂 Folder Structure:

```
~/Devl/docker/hoarder/
├── docker-compose.yml
├── .env
└── README.md
```

---

## 🌱 Environment Variables:

These are defined in `.env`:

| Variable            | Example Value            | Description                                |
|--------------------|--------------------------|--------------------------------------------|
| `HOARDER_VERSION`   | release                  | Hoarder image version                      |
| `NEXTAUTH_SECRET`   | super_random_string      | Secret string for NextAuth                 |
| `MEILI_MASTER_KEY`  | another_random_string    | Master key for MeiliSearch                 |
| `NEXTAUTH_URL`      | http://localhost:3000    | Base URL for Hoarder app                   |

**Generate random strings** for `NEXTAUTH_SECRET` and `MEILI_MASTER_KEY`:

```bash
openssl rand -base64 36
```

---

## 🚀 Full Setup Instructions:

---

### 1️⃣ Create Directory:

```bash
mkdir -p ~/Devl/docker/hoarder
cd ~/Devl/docker/hoarder
```

---

### 2️⃣ Create `.env` File:

```bash
nano .env
```

Example:

```env
HOARDER_VERSION=release
NEXTAUTH_SECRET=super_random_string
MEILI_MASTER_KEY=another_random_string
NEXTAUTH_URL=http://localhost:3000
```

Generate random strings:

```bash
openssl rand -base64 36
```

---

### 3️⃣ Create `docker-compose.yml` File:

```bash
nano docker-compose.yml
```

(See provided file content.)

---

### 4️⃣ Start Hoarder:

```bash
docker compose up -d
```

---

### 5️⃣ Access Hoarder UI:

```
http://localhost:3000
```

---

### 6️⃣ Verify:

```bash
docker ps
docker volume ls
docker network ls
```

You should see:

- **Volume:** `hoarder_data`, `hoarder_meilisearch_data`
- **Network:** `hoarder_network`

---

### 7️⃣ Stop Hoarder (Optional):

```bash
docker compose down
```

---

## ✅ Quick Commands Summary:

```bash
cd ~/Devl/docker/hoarder
docker compose down
docker network prune
docker volume ls
docker network ls
docker compose up -d
http://localhost:3000
```

---

## 🔮 Next Steps:

- Manage Hoarder via Portainer if desired.
- Integrate into your Docker stack.

---
