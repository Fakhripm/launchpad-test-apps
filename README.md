# Launchpad test apps

Open-source JavaScript apps for testing what Launchpad deploys. Each row has at least two apps. Each app is a public copy of its upstream repository, under its own licence.

The rows cover what these Launchpad PRs added:

- [#568](https://github.com/S-Quantum-Engine/launchpad/pull/568): a Node web server on its own.
- [#567](https://github.com/S-Quantum-Engine/launchpad/pull/567): a backend in its own folder beside a front end, with no workspace.
- [#624](https://github.com/S-Quantum-Engine/launchpad/pull/624): a pnpm lock file written by pnpm 7 or 8.

Next.js, single-page apps and workspace backends are left out, since Launchpad deployed them before these PRs.

## Results

Run on Launchpad's local stack (`LAUNCHPAD_TARGET=local`), from #567 and #624 together, on 17 November 2026.

- **Live, no fix needed:** the copy's `main` was deployed again and Launchpad asked for no change to the code.
- **Fails:** the reason is Launchpad's to fix unless the note says the upstream app has a defect.

| Row | App (copy) | Upstream | Licence | Result | Notes |
|---|---|---|---|---|---|
| Express | [lptest-express-typescript](https://github.com/Fakhripm/lptest-express-typescript) | [edwinhern/express-typescript](https://github.com/edwinhern/express-typescript) | MIT | Live, no fix needed | 3 security pins committed |
| Express | [lptest-express-mongodb-rest-api-boilerplate](https://github.com/Fakhripm/lptest-express-mongodb-rest-api-boilerplate) | [watscho/express-mongodb-rest-api-boilerplate](https://github.com/watscho/express-mongodb-rest-api-boilerplate) | MIT | Fails | Its mail worker stops for settings its config schema requires, which Launchpad does not ask for |
| Fastify | [lptest-fastify-api-boilerplate-jwt](https://github.com/Fakhripm/lptest-fastify-api-boilerplate-jwt) | [Tony133/fastify-api-boilerplate-jwt](https://github.com/Tony133/fastify-api-boilerplate-jwt) | MIT | Fails | Settings its `@fastify/env` schema requires are not asked for |
| Fastify | [lptest-fastify-demo](https://github.com/Fakhripm/lptest-fastify-demo) | [fastify/demo](https://github.com/fastify/demo) | MIT | Fails | Its start compiles the code again, and the start-up check gives up first. Listen fix committed |
| Koa | [lptest-node-typescript-koa-rest](https://github.com/Fakhripm/lptest-node-typescript-koa-rest) | [javieraviles/node-typescript-koa-rest](https://github.com/javieraviles/node-typescript-koa-rest) | MIT | Fails | Uses SSL to its database outside development; the database Launchpad runs beside an app has no SSL |
| Koa | [lptest-koa-api-ts-starter](https://github.com/Fakhripm/lptest-koa-api-ts-starter) | [vaso991/koa-api-ts-starter](https://github.com/vaso991/koa-api-ts-starter) | MIT | Fails | Launchpad's repairs moved its start to the source and broke its esbuild config |
| NestJS | [lptest-nestjs-boilerplate](https://github.com/Fakhripm/lptest-nestjs-boilerplate) | [brocoders/nestjs-boilerplate](https://github.com/brocoders/nestjs-boilerplate) | MIT | In progress | Database migration does not finish; `DATABASE_TYPE` set by hand |
| NestJS | [lptest-prime-nestjs](https://github.com/Fakhripm/lptest-prime-nestjs) | [josephgoksu/prime-nestjs](https://github.com/josephgoksu/prime-nestjs) | MIT | Fails | Needs an RSA key pair; settings in its validation class are not read |
| Hapi | [lptest-typescript-hapi-starter](https://github.com/Fakhripm/lptest-typescript-hapi-starter) | [BlackBoxVision/typescript-hapi-starter](https://github.com/BlackBoxVision/typescript-hapi-starter) | MIT | Fails | A dependency installed from GitHub needs `git`, which the build image lacks |
| Hapi | [lptest-nodejs-hapi-template](https://github.com/Fakhripm/lptest-nodejs-hapi-template) | [wednesday-solutions/nodejs-hapi-template](https://github.com/wednesday-solutions/nodejs-hapi-template) | MIT | Fails | Its import aliases were taken for npm packages; its build script is `build:prod` |
| Hono | [lptest-hono-open-api-starter](https://github.com/Fakhripm/lptest-hono-open-api-starter) | [w3cj/hono-open-api-starter](https://github.com/w3cj/hono-open-api-starter) | MIT | Fails | Settings in its zod schema, a SQLite `DATABASE_URL` among them, are not read |
| Hono | [lptest-favicon-api](https://github.com/Fakhripm/lptest-favicon-api) | [vemetric/favicon-api](https://github.com/vemetric/favicon-api) | MIT | Live, no fix needed | Bun |
| h3 | [lptest-feedrender](https://github.com/Fakhripm/lptest-feedrender) | [kiwilan/feedrender](https://github.com/kiwilan/feedrender) | BSD-2-Clause | Live, no fix needed | 3 security pins committed |
| h3 | [lptest-node-server-starter](https://github.com/Fakhripm/lptest-node-server-starter) | [oiij/node-server-starter](https://github.com/oiij/node-server-starter) | MIT | Fails | A leftover `pm2.json` names a file the build never writes. Missing build tools (`rimraf`, `tsup`, an upstream defect) and security fixes committed |
| Elysia | [lptest-elysia-production-template](https://github.com/Fakhripm/lptest-elysia-production-template) | [techfusionid/elysia-production-template](https://github.com/techfusionid/elysia-production-template) | MIT | Live, no fix needed | Bun. 6 security commits. Needs a `RESEND_API_KEY` setting |
| Elysia | [lptest-bun-api-starter](https://github.com/Fakhripm/lptest-bun-api-starter) | [knownasrazi/bun-api-starter](https://github.com/knownasrazi/bun-api-starter) | MIT | Live, no fix needed | Bun; `node_modules` committed upstream |
| AdonisJS | [lptest-adonisjs-boilerplate](https://github.com/Fakhripm/lptest-adonisjs-boilerplate) | [Tagada216/adonisjs-boilerplate](https://github.com/Tagada216/adonisjs-boilerplate) | MIT | Fails | Started from the app's root; AdonisJS starts from `build/` |
| AdonisJS | [lptest-adonis-multi-tenancy-demo](https://github.com/Fakhripm/lptest-adonis-multi-tenancy-demo) | [nedois/adonis-multi-tenancy-demo](https://github.com/nedois/adonis-multi-tenancy-demo) | MIT | Fails | Same as above |
| Encore | none | | | No app | Every licensed Encore.ts app starts only with the Encore CLI's runtime (`encore run`) |
| React (Vite) + Express | [lptest-mern-stack-example](https://github.com/Fakhripm/lptest-mern-stack-example) | [mongodb-developer/mern-stack-example](https://github.com/mongodb-developer/mern-stack-example) | Apache-2.0 | Live, no fix needed | 1 change committed |
| React (Vite) + Express | [lptest-taskflow](https://github.com/Fakhripm/lptest-taskflow) | [KEX-03/taskflow](https://github.com/KEX-03/taskflow) | MIT | Live, no fix needed | Security commits |
| Create React App + Express | [lptest-accountill](https://github.com/Fakhripm/lptest-accountill) | [panshak/accountill](https://github.com/panshak/accountill) | MIT | Fails | webpack 4 fails on Node 22 (OpenSSL) |
| Create React App + Express | [lptest-cinema-plus](https://github.com/Fakhripm/lptest-cinema-plus) | [georgesimos/cinema-plus](https://github.com/georgesimos/cinema-plus) | MIT | Not deployed | Its root `start` runs the server's folder; Launchpad reads the root as a backend it does not run |
| Vue + Express | [lptest-todo-list-vue3-express](https://github.com/Fakhripm/lptest-todo-list-vue3-express) | [yinhr-coder/todo-list-vue3-express](https://github.com/yinhr-coder/todo-list-vue3-express) | MIT | Fails | Imports `vuedraggable` without listing it (an upstream defect); Launchpad does not add it |
| Vue + Express | [lptest-vue-auth-panel](https://github.com/Fakhripm/lptest-vue-auth-panel) | [kianPk/vue-auth-panel](https://github.com/kianPk/vue-auth-panel) | MIT | Live, no fix needed | |
| Front end + NestJS | [lptest-ng-antd-admin](https://github.com/Fakhripm/lptest-ng-antd-admin) | [huajian123/ng-antd-admin](https://github.com/huajian123/ng-antd-admin) | MIT | Fails | Angular. Its path aliases were taken for npm packages |
| Front end + NestJS | [lptest-restaurant](https://github.com/Fakhripm/lptest-restaurant) | [olasunkanmi-SE/restaurant](https://github.com/olasunkanmi-SE/restaurant) | MIT | Fails | Its lock files were removed, and the fresh install broke its type check |
| Front end + Fastify | [lptest-bagre](https://github.com/Fakhripm/lptest-bagre) | [fabgcruz/bagre](https://github.com/fabgcruz/bagre) | MIT | Fails | The API beside the front end needs its Prisma client generated. Security commits |
| Front end + Fastify | [lptest-community-website](https://github.com/Fakhripm/lptest-community-website) | [NEXT-GEN-PROGRAMMING/community-website](https://github.com/NEXT-GEN-PROGRAMMING/community-website) | MIT | Fails | The server beside is started with npm, though it declares pnpm. Security commits |
| pnpm 8 lock file | [lptest-TiantianFundApi](https://github.com/Fakhripm/lptest-TiantianFundApi) | [kouchao/TiantianFundApi](https://github.com/kouchao/TiantianFundApi) | MIT | Live, no fix needed | Installs with pnpm 8. 1 change and 16 security commits |
| pnpm 8 lock file | [lptest-ipdb-API](https://github.com/Fakhripm/lptest-ipdb-API) | [metowolf/ipdb-API](https://github.com/metowolf/ipdb-API) | MIT | Not deployed | Ships a Cloudflare Worker and a Node server; Launchpad reads only the Worker |
| pnpm 8 lock file | [lptest-fastify-jwt-typescript](https://github.com/Fakhripm/lptest-fastify-jwt-typescript) | [thomasjonstrup/fastify-jwt-typescript](https://github.com/thomasjonstrup/fastify-jwt-typescript) | MIT | Fails | Installs with pnpm 8 and runs; the live check asks for `/all` without its route prefix. Listen fix and security pins committed |
| pnpm 7 lock file | [lptest-Habits-Server](https://github.com/Fakhripm/lptest-Habits-Server) | [GabrielGuedess/Habits-Server](https://github.com/GabrielGuedess/Habits-Server) | MIT | Fails | Installs with pnpm 7; its diagram generator then needs a browser |
| pnpm 7 lock file | [lptest-nextjs-stripe-starter](https://github.com/Fakhripm/lptest-nextjs-stripe-starter) | [nhost/nextjs-stripe-starter](https://github.com/nhost/nextjs-stripe-starter) | MIT | Fails | Installs with pnpm 7; the build needs an Nhost project |

## How a copy was made

1. The upstream's default branch was copied with its whole history, as `main`.
2. [gitleaks](https://github.com/gitleaks/gitleaks) v8.21.2 scanned the history before publishing. A repo whose findings were all sample values (example env files, mocks, tests, docs), which the upstream already publishes, was published. A repo with a finding in a real env file was replaced by another app.
3. The upstream's GitHub Actions workflows were removed, and Actions is switched off on every copy.
4. Each app was deployed on Launchpad's local stack. Every security fix Launchpad offered was accepted. Each change Launchpad made to the code (security fixes, its repairs, and build fixes for defects in the upstream app) was committed to the copy with Launchpad's own message, and each touched lock file was brought up to date by the package manager that wrote it. Build fixes that would only hide a Launchpad bug were not accepted.
5. A copy that went live was deployed again from `main`, to check that Launchpad asked for no change.

## Left out

These apps were tested before but have no licence file, so they cannot be published as copies: dhatGuy/PERN-Store, danieljecu/todos_app, vwcwong/pern-stack-template, Yogndrr/MERN-School-Management-System, vercel/nextjs-postgres-auth-starter and TomDoesTech/fastify-prisma-rest-api.

cefjoeii/mern-crud builds its React app into the Express server's `public/` folder. Launchpad does not deploy that layout yet.
