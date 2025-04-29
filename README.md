# Docker VSCode for Full Stack Development

## Production

Build the production images and run them.

```
docker compose -f compose/production.yml up --build
```

Open [https://localhost](https://localhost) to view `frontend` in your browser.

Open [https://localhost/api](https://localhost/api) to view `backend` in your browser.

<!-- ## Development

Build the development images and run them with the host's `UID` and `GID`.

```
UID=$(id -u) GID=$(id -g) docker compose -f compose/development.yml up --build
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

Open [http://localhost:3000](http://localhost:3000) to view it in your browser. -->
