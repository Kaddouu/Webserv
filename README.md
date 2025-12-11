# 🖥️ Webserv – Projet 42

## 🎓 Présentation
Projet réseau du cursus **42Paris**, implémentant un **serveur HTTP/1.1** non-bloquant en **C++98**.  
Le serveur :
- Vérifie et charge un fichier `.conf` passé en argument (ou `conf_file/default.conf` par défaut),
- Parse les *server blocks* via `ServerConf::parseConfigFile()`,
- Initialise un serveur unique ou multiple selon la configuration,
- Lance la boucle principale via `server.run()` (gestion d'événements, `epoll`, sockets, timeouts, requêtes/réponses, CGI).

---

## 🚀 Fonctionnalités principales
- 🔌 Serveur HTTP/1.1 (`GET`, `POST`, `DELETE`)
- 📡 Architecture non-bloquante à base de `epoll`
- 👥 Gestion multi-clients simultanée
- 🗂️ Autoindex, redirections, pages d’erreur
- 📤 Upload de fichiers
- 🧰 Support CGI (Python, PHP, scripts configurés)
- ⚙️ Fichier de configuration style NGINX

---
## 📁 Structure du projet
```bash
webserv/
├── conf_file/
├── include/
├── srcs/
│   ├── CGI/
│   ├── conf/
│   ├── utils/
├── www/
│   ├── api/
│   ├── cgi-bin/
│   ├── custom_uploads/
│   ├── error/
│   ├── put_test/
│   ├── static/
│   ├── test/
│   ├── uploads/
│   ├── videos/
├── Makefile
└── README.md
```
---

## ⚙️ Compilation
```bash
make
````

## ▶️ Exécution

```bash
./webserv conf_file/webserv.conf
```

---

## 🧪 Tests rapides

### Test GET

```bash
curl -v localhost:8080
```

### Test POST upload

```bash
curl -X POST -F "file=@test.txt" localhost:8080/upload
```

### Test CGI

```bash
curl localhost:8080/cgi-bin/test.py
```

---

# 💻 Tech Stack

![C++](https://img.shields.io/badge/c++-%2300599C.svg?style=for-the-badge\&logo=c%2B%2B\&logoColor=white)

---

# 👤 Auteurs

**Ilias Kaddouri**

**Sabry Ferrad**

**Bilal El Halimi**
