# Docker VSCode for Full Stack Development

A Docker workspace for full-stack development with `VSCode Server` on `Alpine Linux`. It keeps the development process consistent from `development` to `production`, and uniform across both `frontend` and `backend` developers.

Say goodbye to "It works on my machine" — and hello to "It works on our machines."

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

Open the project in the terminal using the command:

```
code frontend
```

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

Open the project in the terminal using the command:

```
code backend
```

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

Open the project in the terminal using the command:

```
code frontend
```

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

Open the project in the terminal using the command:

```
code frontend
```

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

A module can be stored in the `modules` folder or included as a Git submodule from another repository.

Here is a module's folder structure:

- `module`
  - `compose`: defines how the containers run
    - `production.yml`
    - `development.yml`
    - `override`
      - `development.yml`
  - `Dockerfile`: defines the image's build process

You can take a look and learn how to define a module from real-world examples such as [backend](https://github.com/VienDinhCom/docker-vscode-backend), [frontend](https://github.com/VienDinhCom/docker-vscode-frontend), or [proxy](https://github.com/VienDinhCom/docker-vscode-fullstack/tree/main/modules/proxy).

## Related Projects

- [Docker VSCode for Back End Development](https://github.com/VienDinhCom/docker-vscode-backend)
- [Docker VSCode for Front End Development](https://github.com/VienDinhCom/docker-vscode-frontend)
- [Docker VSCode for Full Stack Development](https://github.com/VienDinhCom/docker-vscode-fullstack)
