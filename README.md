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

Why do we always assume that “together” is better?

In software, that often means a monorepo. Frontend and backend in one place. Shared code. Shared goals. But also shared problems. More risk. Less clarity. Less control.

Sometimes, moving faster means separating things. Let teams own their space. Their tools. Their boundaries. Collaboration doesn’t have to mean everything is tangled together.

What if you could have both?
Independent teams, but working in sync.
Freedom to move fast, without giving up security.
A setup that works the same for everyone, every time.

That’s the idea behind **Docker VSCode for Full Stack Development**.

It gives you:

* The same dev environment for every developer
* VS Code running in the browser, inside Docker
* No “it works on my machine”
* No local setup beyond Docker
* Frontend and backend separated, but easy to connect
* Dev and prod that behave the same
* A modular setup you can grow or change anytime

Each part stays isolated. Everything comes together only when you want it to.

Simple. Practical. Flexible.

Build together—without forcing everything into one box.


## Related Projects

- [Docker VSCode for Back End Development](https://github.com/VienDinhCom/docker-vscode-backend)
- [Docker VSCode for Front End Development](https://github.com/VienDinhCom/docker-vscode-frontend)
