# Launchpad test apps

Open-source JavaScript apps for testing what Launchpad deploys. Each row has at least two apps. Each app is a public copy of its upstream repository, under its own licence. Launchpad's fixes are already committed to each copy, so a deploy of `main` should need no change to the code.

The rows cover what these Launchpad PRs added:

- [#568](https://github.com/S-Quantum-Engine/launchpad/pull/568): a Node web server on its own.
- [#567](https://github.com/S-Quantum-Engine/launchpad/pull/567): a backend in its own folder beside a front end, with no workspace.
- [#624](https://github.com/S-Quantum-Engine/launchpad/pull/624): a pnpm lock file written by pnpm 7 or 8.

Next.js, single-page apps and workspace backends are left out, since Launchpad deployed them before these PRs.

## Apps

Status is the result on Launchpad's local stack (`LAUNCHPAD_TARGET=local`), with the date of the last run.

| Row | App (copy) | Upstream | Licence | Status | Notes |
|---|---|---|---|---|---|
| Express | [lptest-express-typescript](https://github.com/Fakhripm/lptest-express-typescript) | [edwinhern/express-typescript](https://github.com/edwinhern/express-typescript) | MIT | Not deployed yet | |
| Express | [lptest-express-mongodb-rest-api-boilerplate](https://github.com/Fakhripm/lptest-express-mongodb-rest-api-boilerplate) | [watscho/express-mongodb-rest-api-boilerplate](https://github.com/watscho/express-mongodb-rest-api-boilerplate) | MIT | Not deployed yet | |
| Fastify | [lptest-fastify-api-boilerplate-jwt](https://github.com/Fakhripm/lptest-fastify-api-boilerplate-jwt) | [Tony133/fastify-api-boilerplate-jwt](https://github.com/Tony133/fastify-api-boilerplate-jwt) | MIT | Not deployed yet | |
| Fastify | [lptest-fastify-demo](https://github.com/Fakhripm/lptest-fastify-demo) | [fastify/demo](https://github.com/fastify/demo) | MIT | Not deployed yet | |
| Koa | [lptest-node-typescript-koa-rest](https://github.com/Fakhripm/lptest-node-typescript-koa-rest) | [javieraviles/node-typescript-koa-rest](https://github.com/javieraviles/node-typescript-koa-rest) | MIT | Not deployed yet | |
| Koa | [lptest-koa-api-ts-starter](https://github.com/Fakhripm/lptest-koa-api-ts-starter) | [vaso991/koa-api-ts-starter](https://github.com/vaso991/koa-api-ts-starter) | MIT | Not deployed yet | |
| NestJS | [lptest-nestjs-boilerplate](https://github.com/Fakhripm/lptest-nestjs-boilerplate) | [brocoders/nestjs-boilerplate](https://github.com/brocoders/nestjs-boilerplate) | MIT | Not deployed yet | |
| NestJS | [lptest-prime-nestjs](https://github.com/Fakhripm/lptest-prime-nestjs) | [josephgoksu/prime-nestjs](https://github.com/josephgoksu/prime-nestjs) | MIT | Not deployed yet | |
| Hapi | [lptest-typescript-hapi-starter](https://github.com/Fakhripm/lptest-typescript-hapi-starter) | [BlackBoxVision/typescript-hapi-starter](https://github.com/BlackBoxVision/typescript-hapi-starter) | MIT | Not deployed yet | |
| Hapi | [lptest-nodejs-hapi-template](https://github.com/Fakhripm/lptest-nodejs-hapi-template) | [wednesday-solutions/nodejs-hapi-template](https://github.com/wednesday-solutions/nodejs-hapi-template) | MIT | Not deployed yet | |
| Hono | [lptest-hono-open-api-starter](https://github.com/Fakhripm/lptest-hono-open-api-starter) | [w3cj/hono-open-api-starter](https://github.com/w3cj/hono-open-api-starter) | MIT | Not deployed yet | Node |
| Hono | [lptest-favicon-api](https://github.com/Fakhripm/lptest-favicon-api) | [vemetric/favicon-api](https://github.com/vemetric/favicon-api) | MIT | Not deployed yet | Bun |
| h3 | [lptest-feedrender](https://github.com/Fakhripm/lptest-feedrender) | [kiwilan/feedrender](https://github.com/kiwilan/feedrender) | BSD-2-Clause | Not deployed yet | |
| h3 | [lptest-node-server-starter](https://github.com/Fakhripm/lptest-node-server-starter) | [oiij/node-server-starter](https://github.com/oiij/node-server-starter) | MIT | Not deployed yet | |
| Elysia | [lptest-elysia-production-template](https://github.com/Fakhripm/lptest-elysia-production-template) | [techfusionid/elysia-production-template](https://github.com/techfusionid/elysia-production-template) | MIT | Not deployed yet | Bun |
| Elysia | [lptest-bun-api-starter](https://github.com/Fakhripm/lptest-bun-api-starter) | [knownasrazi/bun-api-starter](https://github.com/knownasrazi/bun-api-starter) | MIT | Not deployed yet | Bun; `node_modules` committed upstream |
| AdonisJS | [lptest-adonisjs-boilerplate](https://github.com/Fakhripm/lptest-adonisjs-boilerplate) | [Tagada216/adonisjs-boilerplate](https://github.com/Tagada216/adonisjs-boilerplate) | MIT | Not deployed yet | |
| AdonisJS | [lptest-adonis-multi-tenancy-demo](https://github.com/Fakhripm/lptest-adonis-multi-tenancy-demo) | [nedois/adonis-multi-tenancy-demo](https://github.com/nedois/adonis-multi-tenancy-demo) | MIT | Not deployed yet | |
| Encore | none | | | No app | Every licensed Encore.ts app starts only with the Encore CLI's runtime (`encore run`), so no repo build can start one. |
| React (Vite) + Express | [lptest-mern-stack-example](https://github.com/Fakhripm/lptest-mern-stack-example) | [mongodb-developer/mern-stack-example](https://github.com/mongodb-developer/mern-stack-example) | Apache-2.0 | Not deployed yet | |
| React (Vite) + Express | [lptest-taskflow](https://github.com/Fakhripm/lptest-taskflow) | [KEX-03/taskflow](https://github.com/KEX-03/taskflow) | MIT | Not deployed yet | |
| Create React App + Express | [lptest-accountill](https://github.com/Fakhripm/lptest-accountill) | [panshak/accountill](https://github.com/panshak/accountill) | MIT | Not deployed yet | |
| Create React App + Express | [lptest-cinema-plus](https://github.com/Fakhripm/lptest-cinema-plus) | [georgesimos/cinema-plus](https://github.com/georgesimos/cinema-plus) | MIT | Not deployed yet | |
| Vue + Express | [lptest-todo-list-vue3-express](https://github.com/Fakhripm/lptest-todo-list-vue3-express) | [yinhr-coder/todo-list-vue3-express](https://github.com/yinhr-coder/todo-list-vue3-express) | MIT | Not deployed yet | |
| Vue + Express | [lptest-vue-auth-panel](https://github.com/Fakhripm/lptest-vue-auth-panel) | [kianPk/vue-auth-panel](https://github.com/kianPk/vue-auth-panel) | MIT | Not deployed yet | |
| Front end + NestJS | [lptest-ng-antd-admin](https://github.com/Fakhripm/lptest-ng-antd-admin) | [huajian123/ng-antd-admin](https://github.com/huajian123/ng-antd-admin) | MIT | Not deployed yet | Angular |
| Front end + NestJS | [lptest-restaurant](https://github.com/Fakhripm/lptest-restaurant) | [olasunkanmi-SE/restaurant](https://github.com/olasunkanmi-SE/restaurant) | MIT | Not deployed yet | |
| Front end + Fastify | [lptest-bagre](https://github.com/Fakhripm/lptest-bagre) | [fabgcruz/bagre](https://github.com/fabgcruz/bagre) | MIT | Not deployed yet | |
| Front end + Fastify | [lptest-community-website](https://github.com/Fakhripm/lptest-community-website) | [NEXT-GEN-PROGRAMMING/community-website](https://github.com/NEXT-GEN-PROGRAMMING/community-website) | MIT | Not deployed yet | |
| pnpm 8 lock file | [lptest-TiantianFundApi](https://github.com/Fakhripm/lptest-TiantianFundApi) | [kouchao/TiantianFundApi](https://github.com/kouchao/TiantianFundApi) | MIT | Not deployed yet | |
| pnpm 8 lock file | [lptest-ipdb-API](https://github.com/Fakhripm/lptest-ipdb-API) | [metowolf/ipdb-API](https://github.com/metowolf/ipdb-API) | MIT | Not deployed yet | |
| pnpm 7 lock file | [lptest-Habits-Server](https://github.com/Fakhripm/lptest-Habits-Server) | [GabrielGuedess/Habits-Server](https://github.com/GabrielGuedess/Habits-Server) | MIT | Not deployed yet | |
| pnpm 7 lock file | [lptest-nextjs-stripe-starter](https://github.com/Fakhripm/lptest-nextjs-stripe-starter) | [nhost/nextjs-stripe-starter](https://github.com/nhost/nextjs-stripe-starter) | MIT | Not deployed yet | Needs Nhost and Stripe keys |

## How a copy was made

1. The upstream's default branch was copied with its whole history, as `main`.
2. [gitleaks](https://github.com/gitleaks/gitleaks) v8.21.2 scanned the history before publishing. A repo whose findings were all sample values (example env files, mocks, tests, docs), which the upstream already publishes, was published, and its row says so. A repo with a finding in a real env file was replaced by another app.
3. Each app was deployed on Launchpad's local stack. Every change Launchpad made to the code (its security fixes, preflight repairs and recipes) was committed to the copy, one commit per change, with its lock file brought up to date. The app was then deployed again from `main` to check that Launchpad asked for nothing.

## Left out

These apps were tested before but have no licence file, so they cannot be published as copies: dhatGuy/PERN-Store, danieljecu/todos_app, vwcwong/pern-stack-template, Yogndrr/MERN-School-Management-System, vercel/nextjs-postgres-auth-starter and TomDoesTech/fastify-prisma-rest-api.

cefjoeii/mern-crud builds its React app into the Express server's `public/` folder. Launchpad does not deploy that layout yet.
