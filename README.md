# Hands-On L3: Multi-Container Microservice with Docker

This project demonstrates the deployment of a **Multi-Container Microservice** using **Docker Desktop** and **Docker Compose**.  
It features a **Python Flask web application** with a **Redis cache**, connected to a **PostgreSQL database**.

---

## 🚀 Prerequisites
- **Docker Desktop**: Ensure you have Docker Desktop installed and running on your system.

---

## ⚙️ Execution Steps

### 1. PostgreSQL Setup
First, set up the PostgreSQL database container.

- **Pull the PostgreSQL image from Docker Hub**:
```
docker pull postgres
```

- **Create and start a new PostgreSQL container**  
The `-d` flag runs it in detached mode, `-p` maps the port, `--name` assigns a name, and `-e` sets environment variables.
```
docker run -d -p 5432:5432 --name postgresql -e POSTGRES_PASSWORD=pass12345 postgres
```

- *(Optional)* **Open a terminal inside the container**:
```
docker exec -it postgresql bash
```

- *(Optional)* **Access the PostgreSQL command-line**:
```
psql -d postgres -U postgres
```

---

### 2. Application Setup
Next, use **Docker Compose** to build and orchestrate the Flask web app and Redis cache.

- **Navigate** to the directory containing your project files (`app.py`, `Dockerfile`, `compose.yaml`, and `requirements.txt`).

- **Build and run the entire application**:
```
docker compose up
```

This will:
- Build the **web service**
- Start both the **web** and **redis containers**  
(as defined in your `compose.yaml` file).

---

### 3. Viewing the Application
Once the services are running, you can view the Flask application in your browser.

👉 Open: [http://localhost:8000](http://localhost:8000)

---

## 🧠 Learning and Reflection
This hands-on exercise was a great introduction to the world of **containerization** and **microservices**.  
Key learnings include:

- **Container Fundamentals**: Understanding how containers isolate applications from their environment.
- **Service Configuration**: Setting up and configuring multiple services (**Python web app**, **Redis**, and **PostgreSQL**) to work together.
- **Multi-Container Orchestration**: Using **Docker Compose** to manage multiple interconnected containers with a single command.
- **System Interconnectivity**: Establishing container networking so that different services can communicate seamlessly.
- **Debugging and Troubleshooting**: Developing skills by intentionally introducing and resolving errors in containerized applications.

---

✅ This project demonstrates a **foundational microservice architecture**, making it easier to scale and manage services independently.
```
