# Docker VSCode for Full Stack Development

## Production

Build the production images and run them.

```
docker compose -f production.yml up --build
```

Open [https://localhost](https://localhost) to view `frontend` or [https://localhost/api](https://localhost/api) to view `backend` in your browser.

## Development

### For Full Stack Developers

Build the development images and run them with the host's `UID` and `GID`.

```
UID=$(id -u) GID=$(id -g) docker compose -f development.yml up --build
```

#### Front End

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

#### Back End

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

Open [http://localhost/api/](http://localhost/api/) to view it in your browser.

### For Front End Developers

Build the development images and run them with the host's `UID` and `GID`.

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

### For Back End Developers

Build the development images and run them with the host's `UID` and `GID`.

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
