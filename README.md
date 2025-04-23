# 🧱 Main Project with Git Submodules and Docker Compose

This repository acts as the main container that orchestrates multiple subprojects (repositories) using **Git Submodules** and runs them using a single `docker-compose.yml` file.

## 📦 Project Structure

```
project-root/
├── ms-auth/         # Backend submodule
├── ms-tasks/        # Backend submodule
├── orchestrator/    # Backend submodule
├── task-app/        # Frontend submodule
├── nginx-taskApp/   # config server reverse proxy
├── docker-compose.yml
└── README.md
```

## 🛠️ Requirements

- [Git](https://git-scm.com/)
- [Docker](https://www.docker.com/)
- [Docker Compose](https://docs.docker.com/compose/)

## 🚀 Getting Started

### 1. Clone the repository with submodules

```bash
git clone --recurse-submodules https://github.com/Aanttrax/project-1.0.0.git
cd project-1.0.0
```

> 💡 If you cloned without `--recurse-submodules`, run:
>
> ```bash
> git submodule update --init --recursive
> ```

### 2. Configure environment variables 

Copy the `.env.example` files in each submodule and create your `.env` file:


### 3. Run the services

```bash
docker compose up --build
```

This will start all services defined in the `docker-compose.yml`.

## 🧩 Included Submodules

| Name      | Path             | Description                      |
|-----------|------------------|----------------------------------|
| ms-auth   | `/ms-auth`       | API to manage authentication     |
| ms-tasks  | `/ms-tasks`      | API to manage CRUD tasks         |
| Backend   | `/orchestrator`  | API or server-side logic         |
| Frontend  | `/task-app`      | Web user interface               |
| Nginx     | `/nginx-taskApp` | Reverse proxy                    |

## 📤 Deployment

This setup can be easily extended for production with:

- Secure `.env` files
- Nginx as reverse proxy
- SSL certificates (Let's Encrypt)

## 🔄 Updating Submodules

When submodules have remote updates:

```bash
git submodule update --remote --merge
```

## 🧑‍💻 Contributing

1. Fork the repository  
2. Clone your fork with submodules:  
   ```bash
   git clone --recurse-submodules <your-fork-url>
   ```
3. Create a new branch and make your changes  
4. Push and open a Pull Request

## 📝 License

This project is licensed under the MIT License. See the `LICENSE` file for more information.

