
<p align="center">
  <a href="http://nestjs.com/" target="blank"><img src="https://nestjs.com/img/logo_text.svg" width="320" alt="Nest Logo" /></a>
</p>

<p align="center">A progressive <a href="http://nodejs.org" target="blank">Node.js</a> framework for building efficient and scalable server-side applications, heavily inspired by <a href="https://angular.io" target="blank">Angular</a>.</p>

<p align="center">
<a href="https://www.npmjs.com/~nestjscore"><img src="https://img.shields.io/npm/v/@nestjs/core.svg" alt="NPM Version" /></a>
<a href="https://www.npmjs.com/~nestjscore"><img src="https://img.shields.io/npm/l/@nestjs/core.svg" alt="Package License" /></a>
<a href="https://travis-ci.org/msanvarov/nest-rest-mongo-boilerplate"><img src="https://travis-ci.org/msanvarov/nest-rest-mongo-boilerplate.svg?branch=master" alt="Travis" /></a>
<a href="https://paypal.me/kamilmysliwiec"><img src="https://img.shields.io/badge/Donate-PayPal-dc3d53.svg"/></a>
<a href="https://twitter.com/nestframework"><img src="https://img.shields.io/twitter/follow/nestframework.svg?style=social&label=Follow"></a>
</p>
    
---

### 📚 Description

This boilerplate is designed to quickly prototype backend applications. It comes pre-configured with essential features like database integration, logging, security, and authentication out of the box.

---

### 🛠️ Prerequisites

#### Non-Docker

- Ensure you have MongoDB installed locally, or configure a cluster using [MongoDB Atlas](https://www.mongodb.com/cloud/atlas). 

#### Docker 🐳

- Make sure Docker Desktop is set up on your preferred OS to easily run the app. You can also use [Docker Toolbox](https://docs.docker.com/toolbox/toolbox_install_windows/) on Windows versions that don't support Docker Desktop.

---

### 🚀 Deployment

#### Manual Deployment without Docker

1. Create a `.env` file using `cp .env.example .env` and replace the environment variables with your personal settings (MongoDB URL, etc.).

2. Install dependencies using `npm i` or `yarn`.

3. Start the app in development mode using `npm run start:dev` or in production mode using `npm run start`.

#### Deployment with Docker 🐳

1. In the app directory, run the following command:

   ```bash
   # Create and launch Docker containers with required configurations
   $ docker-compose up -d
   ```

2. The app will be exposed on `http://localhost:9000` and MongoDB on `http://localhost:27017`.

---

### 🔒 Environment Configuration

- **APP_ENV**: Defines the application environment (development/production).
- **APP_URL**: Base URL for the application (for `ConfigService`).
- **WEBTOKEN_SECRET_KEY**: Secret key for JWT encryption/decryption.
- **WEBTOKEN_EXPIRATION_TIME**: Time in seconds for the token to expire.
- **DB_URL**: MongoDB connection URL.

---

### 🏗 Choosing a Web Framework

This boilerplate comes pre-configured with [Fastify](https://github.com/fastify/fastify) for performance benefits, but you can switch to [Express](https://expressjs.com/) if needed.

#### Fastify Configuration:
```ts
import { FastifyAdapter, NestFastifyApplication } from '@nestjs/platform-fastify';
const app = await NestFactory.create<NestFastifyApplication>(AppModule, new FastifyAdapter());
```

#### Express Configuration:
```ts
import * as helmet from 'helmet';
const app = await NestFactory.create(AppModule);
app.use(helmet());
```

---

### ✅ Testing

#### Docker 🐳
```bash
# Run unit tests
$ docker exec -it nest yarn test

# Run e2e tests
$ docker exec -it nest yarn test:e2e
```

#### Non-Docker
```bash
# Run unit tests
$ npm run test

# Run e2e tests
$ npm run test:e2e
```

---

### 💡 TypeDocs

Generate TypeScript documentation using the following command:
```bash
$ npm run typedocs
```

---

### 📝 OpenAPI (Swagger)

This boilerplate includes **Swagger** for API documentation. Configuration can be found in the `swagger` folder.

---

### ✨ Mongoose

Mongoose is included for MongoDB object modeling. Refer to [Mongoose documentation](https://mongoosejs.com) for more details.

---

### 🔊 Logging

This boilerplate includes the **Winston** logging library. Configuration can be found in the `app.module.ts`.

---

### 👥 Support

Nest has grown thanks to sponsors and backers. You can [support NestJS](https://docs.nestjs.com/support).

---

## License

Nest is [MIT licensed](LICENSE).

## Author

Created and maintained by [Milad Ahmadi](https://github.com/milad-ahmd).
