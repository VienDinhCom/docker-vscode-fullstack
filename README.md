# Docker VSCode for Full Stack Development

A Docker workspace for full-stack development using `VSCode Server` on `Alpine Linux` containers. It ensures a consistent development process from `development` to `production` and provides a uniform environment for both `frontend` and `backend` developers.

- 🐳 **Just Docker**—no local dependencies
- 🖥️ **VSCode in browser**—run and code, no setup
- 🧩 **Modular**—easy backend/frontend/proxy swaps
- 🚀 **Effortless dev-to-prod workflow**—deploy what you build
- ⚡ **Consistent environments**—no more `it works on my machine`

Perfect for fast, reliable, and collaborative full-stack development!

## Modules

A project can have two, three, or many modules. These can be defined in the `modules` folder or included as a Git submodule.

Here's what we have in this project:

- [backend](https://github.com/VienDinhCom/docker-vscode-backend): APIs and services such as databases, caching, etc.
- [frontend](https://github.com/VienDinhCom/docker-vscode-frontend): The UI of the application interacting with the APIs.
- [proxy](https://github.com/VienDinhCom/docker-vscode-fullstack/tree/main/modules/proxy): The reverse proxy that combines the `backend` and `frontend`.

You can learn how to define a module here: [define a module](#define-a-module).

## Installation

Before using this project, make sure you have `Docker CLI` version `1.27.0` or higher, with built-in `compose` support.

```
git clone --recurse-submodules https://github.com/VienDinhCom/docker-vscode-fullstack.git
```

The command above clones the project itself and all its [modules](https://github.com/VienDinhCom/docker-vscode-fullstack/tree/main/modules), such as [backend](https://github.com/VienDinhCom/docker-vscode-backend) and [frontend](https://github.com/VienDinhCom/docker-vscode-frontend), from other repositories.

## Production

Build the production images and run them.

```
docker compose -f production.yml up --build
```

Open [https://localhost](https://localhost) to view `frontend` or [https://localhost/api](https://localhost/api) to view `backend` in your browser.

## Full Stack Development

Build the development images and run them with the host's `UID` and `GID` in `fullstack` mode.

```
UID=$(id -u) GID=$(id -g) docker compose -f development.yml up --build
```

### Front End

Open [http://localhost:53000](http://localhost:53000) to develop inside the container with Visual Studio Code directly in your browser.

Install project dependencies.

```
npm install
```

Run the app in the development mode.

```
npm run dev
```

Open [https://localhost/](https://localhost/) to view it in your browser.

### Back End

Open [http://localhost:58000](http://localhost:58000) to develop inside the container with Visual Studio Code directly in your browser.

Install project dependencies.

```
npm install
```

Run the app in the development mode.

```
npm run dev
```

Open [https://localhost/api/](https://localhost/api/) to view it in your browser.

## Front End Development

Build the development images and run them with the host's `UID` and `GID` in `frontend` mode.

```
UID=$(id -u) GID=$(id -g) docker compose -f development.frontend.yml up --build
```

Open [http://localhost:53000](http://localhost:53000) to develop inside the container with Visual Studio Code directly in your browser.

Install project dependencies.

```
npm install
```

Run the app in the development mode.

```
npm run dev
```

Open [https://localhost/](https://localhost/) to view it in your browser.

## Back End Development

Build the development images and run them with the host's `UID` and `GID` in `backend` mode.

```
UID=$(id -u) GID=$(id -g) docker compose -f development.backend.yml up --build
```

Open [http://localhost:58000](http://localhost:58000) to develop inside the container with Visual Studio Code directly in your browser.

Install project dependencies.

```
npm install
```

Run the app in the development mode.

```
npm run dev
```

Open [https://localhost/api/](https://localhost/api/) to view it in your browser.

## Define a Module

A module is stored in the `modules` folder or included as a Git submodule from another repository.

Here is a module's folder structure:

- `module`
  - `docker`: defines how the containers run
    - `image`
      - `dockerfile`
      - `production/endpoint/start`
      - `development/endpoint/start`
    - `production.yml`
    - `development.yml`
    - `override`
      - `development.yml`
    
  - `...`: the rest of your module files

You can take a look and learn how to define a module from real-world examples such as [backend](https://github.com/VienDinhCom/docker-vscode-backend), [frontend](https://github.com/VienDinhCom/docker-vscode-frontend), or [proxy](https://github.com/VienDinhCom/docker-vscode-fullstack/tree/main/modules/proxy).

## Philosophy

Why do we always assume together is better?

You’ve heard it: monorepo. The promise of unity. Backend and frontend, side by side. Shared code, shared vision, shared headaches. Collaboration, yes. But also, entanglement. The more we merge, the more we risk—security, autonomy, clarity. Sometimes, the best way to build is to separate. To let each team own their space, their process, their boundaries.

You want the freedom to move fast, but you also want control. You want to collaborate, but not at the cost of security. You want a system that adapts to your needs, not the other way around.

So, what if you could have both? What if you could keep your teams independent, yet still work in harmony? What if your development environment was always consistent, always ready, always yours—no matter where you are or what you’re building?

That’s the philosophy behind **Docker VSCode for Full Stack Development**. Modular. Isolated. Unified only when you choose. No more `it works on my machine`. No more compromise between collaboration and security. Just a practical, minimal, and powerful way to build—together, apart.

## How Does the Project Help You?

#### Consistent Dev Environments

Spin up a full-stack development environment in seconds—no more `it works on my machine` headaches. Every developer gets the same stack, from backend to frontend, every time.

#### VSCode in the Browser

Develop directly inside your containers using Visual Studio Code, accessible from your browser. No local setup on your machines—just code, anywhere.

#### Modular Architecture

Easily add, remove, or update modules (like backend, frontend, or proxy) as your project grows. Use the built-in modules or bring your own via Git submodules.

#### Seamless Transition from Dev to Prod

Build and run your stack in both development and production modes with a single command. What you test locally is exactly what you’ll deploy.

#### Zero Local Dependencies

All you need is Docker. No Node, Python, or other runtimes required on your machine. Your stack, your way, on any OS.

#### UID/GID Mapping for File Safety

Run containers with your host’s user and group IDs to avoid permission issues and keep your files safe and accessible.

#### Real-World Examples Included

Jumpstart your project with ready-to-use backend, frontend, and proxy modules. Learn by example or use them as templates for your own services.

#### Easy Module Definition

Define new modules with a simple folder structure. Plug them into your stack with minimal configuration.

#### Unified Workflow for Teams

Frontend and backend developers work in harmony, using the same tools and processes. Collaboration has never been smoother.

#### Open Source and Extensible

Fork, extend, and contribute. This project is designed to grow with your needs and the open-source community.

## Related Projects

- [Docker VSCode for Back End Development](https://github.com/VienDinhCom/docker-vscode-backend)
- [Docker VSCode for Front End Development](https://github.com/VienDinhCom/docker-vscode-frontend)
