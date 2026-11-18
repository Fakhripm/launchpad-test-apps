# Launchpad test apps

Open-source JavaScript apps for testing what Launchpad deploys. Each row has at least two apps. Each app is a public copy of its upstream repository, under its own licence.

The rows cover what these Launchpad PRs added:

- [#568](https://github.com/S-Quantum-Engine/launchpad/pull/568): a Node web server on its own.
- [#567](https://github.com/S-Quantum-Engine/launchpad/pull/567): a backend in its own folder beside a front end, with no workspace.
- [#624](https://github.com/S-Quantum-Engine/launchpad/pull/624): a pnpm lock file written by pnpm 7 or 8.

Next.js, single-page apps and workspace backends are left out, since Launchpad deployed them before these PRs.

## Results

Run on Launchpad's local stack (`LAUNCHPAD_TARGET=local`), from #567 and #624 together, finished on 18 November 2026. All 33 apps went live. Each failure on the way was fixed in a Launchpad rule, never in the app, and #567 holds those rules.

- **Live:** the app passed Launchpad's live check. No change was made to an app by hand.
- **Launchpad commits:** the changes Launchpad made to the app's code (its repairs, build fixes and the security fixes it offered), each accepted and replayed onto the copy as Launchpad's own commit.
- **Notes:** for an app that failed first, the rule in #567 that made it go live.

| Row | App (copy) | Upstream | Licence | Runtime | Package manager | Result | Launchpad commits | Notes |
|---|---|---|---|---|---|---|---|---|
| Express | [lptest-express-typescript](https://github.com/Fakhripm/lptest-express-typescript) | [edwinhern/express-typescript](https://github.com/edwinhern/express-typescript) | MIT | Node (unpinned: 22) | pnpm 10 | Live | 4 | Security pins |
| Express | [lptest-express-mongodb-rest-api-boilerplate](https://github.com/Fakhripm/lptest-express-mongodb-rest-api-boilerplate) | [watscho/express-mongodb-rest-api-boilerplate](https://github.com/watscho/express-mongodb-rest-api-boilerplate) | MIT | Node 26.13.0 | yarn 4 | Live | 0 | The Redis is given under every `REDIS_*` name the code reads (`REDIS_URI`); a compose command that runs once is not a worker |
| Fastify | [lptest-fastify-api-boilerplate-jwt](https://github.com/Fakhripm/lptest-fastify-api-boilerplate-jwt) | [Tony133/fastify-api-boilerplate-jwt](https://github.com/Tony133/fastify-api-boilerplate-jwt) | MIT | Node (unpinned: 22) | npm | Live | 1 | |
| Fastify | [lptest-fastify-demo](https://github.com/Fakhripm/lptest-fastify-demo) | [fastify/demo](https://github.com/fastify/demo) | MIT | Node (unpinned: 22) | npm (no lock file) | Live | 3 | Listen fix |
| Koa | [lptest-node-typescript-koa-rest](https://github.com/Fakhripm/lptest-node-typescript-koa-rest) | [javieraviles/node-typescript-koa-rest](https://github.com/javieraviles/node-typescript-koa-rest) | MIT | Node 14.x.x | npm | Live | 17 | An npm 6 lock file is installed by npm 6, and no security pin goes on it |
| Koa | [lptest-koa-api-ts-starter](https://github.com/Fakhripm/lptest-koa-api-ts-starter) | [vaso991/koa-api-ts-starter](https://github.com/vaso991/koa-api-ts-starter) | MIT | Node (unpinned: 22) | npm (no lock file) | Live | 1 | |
| NestJS | [lptest-nestjs-boilerplate](https://github.com/Fakhripm/lptest-nestjs-boilerplate) | [brocoders/nestjs-boilerplate](https://github.com/brocoders/nestjs-boilerplate) | MIT | Node 24.14.1 | npm | Live | 11 | The start-up check gets every example value the live app gets (`DATABASE_TYPE`) |
| NestJS | [lptest-prime-nestjs](https://github.com/Fakhripm/lptest-prime-nestjs) | [josephgoksu/prime-nestjs](https://github.com/josephgoksu/prime-nestjs) | MIT | Node ^22.13.0 \|\| >=24.11.0 | npm | Live | 1 | |
| Hapi | [lptest-typescript-hapi-starter](https://github.com/Fakhripm/lptest-typescript-hapi-starter) | [BlackBoxVision/typescript-hapi-starter](https://github.com/BlackBoxVision/typescript-hapi-starter) | MIT | Node >=10.0 | npm | Live | 22 | hapi before 20.2.1, which stops on its first request on Node 16 and later, is raised with its types |
| Hapi | [lptest-nodejs-hapi-template](https://github.com/Fakhripm/lptest-nodejs-hapi-template) | [wednesday-solutions/nodejs-hapi-template](https://github.com/wednesday-solutions/nodejs-hapi-template) | MIT | Node (unpinned: 22) | yarn 1 | Live | 13 | Yarn 1 installs with `--ignore-engines`; hapi's `catbox-redis` counts as a Redis client, which is sent the Redis's password |
| Hono | [lptest-hono-open-api-starter](https://github.com/Fakhripm/lptest-hono-open-api-starter) | [w3cj/hono-open-api-starter](https://github.com/w3cj/hono-open-api-starter) | MIT | Node (unpinned: 22) | pnpm 10 | Live | 2 | |
| Hono | [lptest-favicon-api](https://github.com/Fakhripm/lptest-favicon-api) | [vemetric/favicon-api](https://github.com/vemetric/favicon-api) | MIT | Bun | bun | Live | 0 | Bun |
| h3 | [lptest-feedrender](https://github.com/Fakhripm/lptest-feedrender) | [kiwilan/feedrender](https://github.com/kiwilan/feedrender) | BSD-2-Clause | Node (unpinned: 22) | pnpm 10 | Live | 11 | |
| h3 | [lptest-node-server-starter](https://github.com/Fakhripm/lptest-node-server-starter) | [oiij/node-server-starter](https://github.com/oiij/node-server-starter) | MIT | Node (unpinned: 22) | pnpm 10 | Live | 7 | Missing build tools (`rimraf`, `tsup`, an upstream defect) |
| Elysia | [lptest-elysia-production-template](https://github.com/Fakhripm/lptest-elysia-production-template) | [techfusionid/elysia-production-template](https://github.com/techfusionid/elysia-production-template) | MIT | Bun | bun | Live | 6 | Bun. Needs a `RESEND_API_KEY` setting |
| Elysia | [lptest-bun-api-starter](https://github.com/Fakhripm/lptest-bun-api-starter) | [knownasrazi/bun-api-starter](https://github.com/knownasrazi/bun-api-starter) | MIT | Bun | bun | Live | 0 | Bun; `node_modules` committed upstream |
| AdonisJS | [lptest-adonisjs-boilerplate](https://github.com/Fakhripm/lptest-adonisjs-boilerplate) | [Tagada216/adonisjs-boilerplate](https://github.com/Tagada216/adonisjs-boilerplate) | MIT | Node (unpinned: 22) | npm | Live | 7 | The start-up check's stand-in for a `*_HOST` is `localhost` |
| AdonisJS | [lptest-adonis-multi-tenancy-demo](https://github.com/Fakhripm/lptest-adonis-multi-tenancy-demo) | [nedois/adonis-multi-tenancy-demo](https://github.com/nedois/adonis-multi-tenancy-demo) | MIT | Node (unpinned: 22) | npm | Live | 7 | The Redis under every name its schema reads (`QUEUE_REDIS_HOST`), with a database number |
| Encore | none | | | | | No app | | Every licensed Encore.ts app starts only with the Encore CLI's runtime (`encore run`) |
| React (Vite) + Express | [lptest-mern-stack-example](https://github.com/Fakhripm/lptest-mern-stack-example) | [mongodb-developer/mern-stack-example](https://github.com/mongodb-developer/mern-stack-example) | Apache-2.0 | Node (unpinned: 22) | npm | Live | 1 | |
| React (Vite) + Express | [lptest-taskflow](https://github.com/Fakhripm/lptest-taskflow) | [KEX-03/taskflow](https://github.com/KEX-03/taskflow) | MIT | Node 24 | npm | Live | 5 | |
| Create React App + Express | [lptest-accountill](https://github.com/Fakhripm/lptest-accountill) | [panshak/accountill](https://github.com/panshak/accountill) | MIT | Node (unpinned: 22) | npm | Live | 6 | An npm 6 lock file is installed by npm 6 |
| Create React App + Express | [lptest-cinema-plus](https://github.com/Fakhripm/lptest-cinema-plus) | [georgesimos/cinema-plus](https://github.com/georgesimos/cinema-plus) | MIT | Node (unpinned: 22) | npm (no lock file) | Live | 1 | A part with no lock file gets `git` in its build stage; `node-sass` is swapped for `sass` |
| Vue + Express | [lptest-todo-list-vue3-express](https://github.com/Fakhripm/lptest-todo-list-vue3-express) | [yinhr-coder/todo-list-vue3-express](https://github.com/yinhr-coder/todo-list-vue3-express) | MIT | Node ^20.19.0 \|\| >=22.12.0 | npm | Live | 14 | |
| Vue + Express | [lptest-vue-auth-panel](https://github.com/Fakhripm/lptest-vue-auth-panel) | [kianPk/vue-auth-panel](https://github.com/kianPk/vue-auth-panel) | MIT | Node (unpinned: 22) | npm | Live | 0 | |
| Front end + NestJS | [lptest-ng-antd-admin](https://github.com/Fakhripm/lptest-ng-antd-admin) | [huajian123/ng-antd-admin](https://github.com/huajian123/ng-antd-admin) | MIT | Node (unpinned: 22) | npm 11, npm | Live | 8 | Drizzle's migrate with no migrations shipped is no release step |
| Front end + NestJS | [lptest-restaurant](https://github.com/Fakhripm/lptest-restaurant) | [olasunkanmi-SE/restaurant](https://github.com/olasunkanmi-SE/restaurant) | MIT | Node (unpinned: 22) | npm | Live | 9 | |
| Front end + Fastify | [lptest-bagre](https://github.com/Fakhripm/lptest-bagre) | [fabgcruz/bagre](https://github.com/fabgcruz/bagre) | MIT | Node >=20 | npm | Live | 9 | |
| Front end + Fastify | [lptest-community-website](https://github.com/Fakhripm/lptest-community-website) | [NEXT-GEN-PROGRAMMING/community-website](https://github.com/NEXT-GEN-PROGRAMMING/community-website) | MIT | Node (unpinned: 22) | pnpm 11, pnpm 10 | Live | 20 | A package released in lockstep with a pinned sibling (`vue`) is set to the pinned version |
| pnpm 8 lock file | [lptest-TiantianFundApi](https://github.com/Fakhripm/lptest-TiantianFundApi) | [kouchao/TiantianFundApi](https://github.com/kouchao/TiantianFundApi) | MIT | Node (unpinned: 22) | pnpm 8 | Live | 18 | Installs with pnpm 8 |
| pnpm 8 lock file | [lptest-ipdb-API](https://github.com/Fakhripm/lptest-ipdb-API) | [metowolf/ipdb-API](https://github.com/metowolf/ipdb-API) | MIT | Node (unpinned: 22) | pnpm 8 | Live | 1 | |
| pnpm 8 lock file | [lptest-fastify-jwt-typescript](https://github.com/Fakhripm/lptest-fastify-jwt-typescript) | [thomasjonstrup/fastify-jwt-typescript](https://github.com/thomasjonstrup/fastify-jwt-typescript) | MIT | Node (unpinned: 22) | pnpm 8 | Live | 5 | Installs with pnpm 8. Listen fix and security pins |
| pnpm 7 lock file | [lptest-Habits-Server](https://github.com/Fakhripm/lptest-Habits-Server) | [GabrielGuedess/Habits-Server](https://github.com/GabrielGuedess/Habits-Server) | MIT | Node (unpinned: 22) | pnpm 7 | Live | 8 | Installs with pnpm 7 |
| pnpm 7 lock file | [lptest-nextjs-stripe-starter](https://github.com/Fakhripm/lptest-nextjs-stripe-starter) | [nhost/nextjs-stripe-starter](https://github.com/nhost/nextjs-stripe-starter) | MIT | Node (unpinned: 22) | pnpm 7 | Live | 15 | Installs with pnpm 7 |

## How a copy was made

1. The upstream's default branch was copied with its whole history, as `main`.
2. [gitleaks](https://github.com/gitleaks/gitleaks) v8.21.2 scanned the history before publishing. A repo whose findings were all sample values (example env files, mocks, tests, docs), which the upstream already publishes, was published. A repo with a finding in a real env file was replaced by another app.
3. The upstream's GitHub Actions workflows were removed, and Actions is switched off on every copy.
4. Each app was deployed on Launchpad's local stack. Settings Launchpad asked the owner for were answered with the values in the app's own example files, or a placeholder where the file has none. Every security fix Launchpad offered was accepted. Each change Launchpad made to the code (security fixes, its repairs, and build fixes for defects in the upstream app) was committed to the copy with Launchpad's own message, and each touched lock file was brought up to date by the package manager that wrote it. Build fixes that would only hide a Launchpad bug were not accepted: the bug was fixed in Launchpad's rules instead.

## Left out

These apps were tested before but have no licence file, so they cannot be published as copies: dhatGuy/PERN-Store, danieljecu/todos_app, vwcwong/pern-stack-template, Yogndrr/MERN-School-Management-System, vercel/nextjs-postgres-auth-starter and TomDoesTech/fastify-prisma-rest-api.

cefjoeii/mern-crud builds its React app into the Express server's `public/` folder. Launchpad does not deploy that layout yet.
