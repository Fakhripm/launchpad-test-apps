# Launchpad test apps

Open-source JavaScript apps for testing what Launchpad deploys. Each row has at least two apps. Each app is a public copy of its upstream repository, under its own licence.

The rows cover what these Launchpad PRs added:

- [#568](https://github.com/S-Quantum-Engine/launchpad/pull/568): a Node web server on its own.
- [#567](https://github.com/S-Quantum-Engine/launchpad/pull/567): a backend in its own folder beside a front end, with no workspace.
- [#624](https://github.com/S-Quantum-Engine/launchpad/pull/624): a pnpm lock file written by pnpm 7 or 8.

Next.js, single-page apps and workspace backends are left out, since Launchpad deployed them before these PRs.

## Results

Run on Launchpad's local stack (`LAUNCHPAD_TARGET=local`), from #567 and #624 together, on 18 November 2026. 17 of 33 apps are live. #567 holds a rule for the cause of each of the other 16, and they are being deployed again with those rules.

- **Live:** the app passed Launchpad's live check. Every change Launchpad made to its code (its repairs, the build fixes and the security fixes it offered) was accepted and replayed onto the copy as Launchpad's own commits. No change was made to an app by hand.
- **In progress:** the app failed its last deploy. The note names the cause and the rule #567 now has for it, which is not yet proven live.

| Row | App (copy) | Upstream | Licence | Runtime | Package manager | Result | Notes |
|---|---|---|---|---|---|---|---|
| Express | [lptest-express-typescript](https://github.com/Fakhripm/lptest-express-typescript) | [edwinhern/express-typescript](https://github.com/edwinhern/express-typescript) | MIT | Node (unpinned: 22) | pnpm 10 | Live | 3 security pins committed |
| Express | [lptest-express-mongodb-rest-api-boilerplate](https://github.com/Fakhripm/lptest-express-mongodb-rest-api-boilerplate) | [watscho/express-mongodb-rest-api-boilerplate](https://github.com/watscho/express-mongodb-rest-api-boilerplate) | MIT | Node 26.13.0 | yarn 4 | In progress | Reads its Redis as `REDIS_URI`, which Launchpad left unset. Rule: the Redis is given under every `REDIS_*` name the code reads |
| Fastify | [lptest-fastify-api-boilerplate-jwt](https://github.com/Fakhripm/lptest-fastify-api-boilerplate-jwt) | [Tony133/fastify-api-boilerplate-jwt](https://github.com/Tony133/fastify-api-boilerplate-jwt) | MIT | Node (unpinned: 22) | npm | Live | |
| Fastify | [lptest-fastify-demo](https://github.com/Fakhripm/lptest-fastify-demo) | [fastify/demo](https://github.com/fastify/demo) | MIT | Node (unpinned: 22) | npm (no lock file) | Live | Listen fix committed |
| Koa | [lptest-node-typescript-koa-rest](https://github.com/Fakhripm/lptest-node-typescript-koa-rest) | [javieraviles/node-typescript-koa-rest](https://github.com/javieraviles/node-typescript-koa-rest) | MIT | Node 14.x.x | npm | In progress | Its npm 6 lock file was laid out again by a newer npm, and its lint found the wrong `js-yaml`. Rule: an npm 6 lock file is installed by npm 6 |
| Koa | [lptest-koa-api-ts-starter](https://github.com/Fakhripm/lptest-koa-api-ts-starter) | [vaso991/koa-api-ts-starter](https://github.com/vaso991/koa-api-ts-starter) | MIT | Node (unpinned: 22) | npm (no lock file) | In progress | Built and started; the live check timed out while the local stack restarted |
| NestJS | [lptest-nestjs-boilerplate](https://github.com/Fakhripm/lptest-nestjs-boilerplate) | [brocoders/nestjs-boilerplate](https://github.com/brocoders/nestjs-boilerplate) | MIT | Node 24.14.1 | npm | In progress | The start-up check left `DATABASE_TYPE` unset, which only its example file names. Rule: the check gets every example value the live app gets |
| NestJS | [lptest-prime-nestjs](https://github.com/Fakhripm/lptest-prime-nestjs) | [josephgoksu/prime-nestjs](https://github.com/josephgoksu/prime-nestjs) | MIT | Node ^22.13.0 \|\| >=24.11.0 | npm | Live | |
| Hapi | [lptest-typescript-hapi-starter](https://github.com/Fakhripm/lptest-typescript-hapi-starter) | [BlackBoxVision/typescript-hapi-starter](https://github.com/BlackBoxVision/typescript-hapi-starter) | MIT | Node >=10.0 | npm | In progress | hapi 19 stops on its first request on Node 16 and later. Rule: Launchpad raises it to 20.2.1; its types package is next |
| Hapi | [lptest-nodejs-hapi-template](https://github.com/Fakhripm/lptest-nodejs-hapi-template) | [wednesday-solutions/nodejs-hapi-template](https://github.com/wednesday-solutions/nodejs-hapi-template) | MIT | Node (unpinned: 22) | yarn 1 | In progress | Yarn 1 stopped on a dependency that asks for Node 18 or 20. Rule: Yarn 1 installs with `--ignore-engines` |
| Hono | [lptest-hono-open-api-starter](https://github.com/Fakhripm/lptest-hono-open-api-starter) | [w3cj/hono-open-api-starter](https://github.com/w3cj/hono-open-api-starter) | MIT | Node (unpinned: 22) | pnpm 10 | In progress | Its last build ran while the local stack restarted |
| Hono | [lptest-favicon-api](https://github.com/Fakhripm/lptest-favicon-api) | [vemetric/favicon-api](https://github.com/vemetric/favicon-api) | MIT | Bun | bun | Live | Bun |
| h3 | [lptest-feedrender](https://github.com/Fakhripm/lptest-feedrender) | [kiwilan/feedrender](https://github.com/kiwilan/feedrender) | BSD-2-Clause | Node (unpinned: 22) | pnpm 10 | Live | 3 security pins committed |
| h3 | [lptest-node-server-starter](https://github.com/Fakhripm/lptest-node-server-starter) | [oiij/node-server-starter](https://github.com/oiij/node-server-starter) | MIT | Node (unpinned: 22) | pnpm 10 | Live | Missing build tools (`rimraf`, `tsup`, an upstream defect) and security fixes committed |
| Elysia | [lptest-elysia-production-template](https://github.com/Fakhripm/lptest-elysia-production-template) | [techfusionid/elysia-production-template](https://github.com/techfusionid/elysia-production-template) | MIT | Bun | bun | Live | Bun. 6 security commits. Needs a `RESEND_API_KEY` setting |
| Elysia | [lptest-bun-api-starter](https://github.com/Fakhripm/lptest-bun-api-starter) | [knownasrazi/bun-api-starter](https://github.com/knownasrazi/bun-api-starter) | MIT | Bun | bun | Live | Bun; `node_modules` committed upstream |
| AdonisJS | [lptest-adonisjs-boilerplate](https://github.com/Fakhripm/lptest-adonisjs-boilerplate) | [Tagada216/adonisjs-boilerplate](https://github.com/Tagada216/adonisjs-boilerplate) | MIT | Node (unpinned: 22) | npm | In progress | The start-up check's stand-in host failed a lookup. Rule: a stand-in `*_HOST` is `localhost` |
| AdonisJS | [lptest-adonis-multi-tenancy-demo](https://github.com/Fakhripm/lptest-adonis-multi-tenancy-demo) | [nedois/adonis-multi-tenancy-demo](https://github.com/nedois/adonis-multi-tenancy-demo) | MIT | Node (unpinned: 22) | npm | In progress | Its schema refused a URL for `QUEUE_REDIS_HOST` and `QUEUE_REDIS_DB`. Rules: the Redis names, a stand-in host and a cache's database number |
| Encore | none | | |  |  | No app | Every licensed Encore.ts app starts only with the Encore CLI's runtime (`encore run`) |
| React (Vite) + Express | [lptest-mern-stack-example](https://github.com/Fakhripm/lptest-mern-stack-example) | [mongodb-developer/mern-stack-example](https://github.com/mongodb-developer/mern-stack-example) | Apache-2.0 | Node (unpinned: 22) | npm | Live | 1 change committed |
| React (Vite) + Express | [lptest-taskflow](https://github.com/Fakhripm/lptest-taskflow) | [KEX-03/taskflow](https://github.com/KEX-03/taskflow) | MIT | Node 24 | npm | Live | Security commits |
| Create React App + Express | [lptest-accountill](https://github.com/Fakhripm/lptest-accountill) | [panshak/accountill](https://github.com/panshak/accountill) | MIT | Node (unpinned: 22) | npm | In progress | Its npm 6 lock file was laid out again by a newer npm, and its build found an old `semver`. Rule: an npm 6 lock file is installed by npm 6 |
| Create React App + Express | [lptest-cinema-plus](https://github.com/Fakhripm/lptest-cinema-plus) | [georgesimos/cinema-plus](https://github.com/georgesimos/cinema-plus) | MIT | Node (unpinned: 22) | npm (no lock file) | In progress | With no lock file, a dependency fetched from Git needed `git`. Rule: a part with no lock file gets `git` in its build stage |
| Vue + Express | [lptest-todo-list-vue3-express](https://github.com/Fakhripm/lptest-todo-list-vue3-express) | [yinhr-coder/todo-list-vue3-express](https://github.com/yinhr-coder/todo-list-vue3-express) | MIT | Node ^20.19.0 \|\| >=22.12.0 | npm | Live | 11 Launchpad commits |
| Vue + Express | [lptest-vue-auth-panel](https://github.com/Fakhripm/lptest-vue-auth-panel) | [kianPk/vue-auth-panel](https://github.com/kianPk/vue-auth-panel) | MIT | Node (unpinned: 22) | npm | Live | |
| Front end + NestJS | [lptest-ng-antd-admin](https://github.com/Fakhripm/lptest-ng-antd-admin) | [huajian123/ng-antd-admin](https://github.com/huajian123/ng-antd-admin) | MIT | Node (unpinned: 22) | npm 11, npm | In progress | Its release step ran Drizzle's migrate with no migrations shipped. Rule: that is no release step |
| Front end + NestJS | [lptest-restaurant](https://github.com/Fakhripm/lptest-restaurant) | [olasunkanmi-SE/restaurant](https://github.com/olasunkanmi-SE/restaurant) | MIT | Node (unpinned: 22) | npm | In progress | Deploying again on the new rules |
| Front end + Fastify | [lptest-bagre](https://github.com/Fakhripm/lptest-bagre) | [fabgcruz/bagre](https://github.com/fabgcruz/bagre) | MIT | Node >=20 | npm | In progress | Went live on 18 November, then was deleted by mistake; deploying again |
| Front end + Fastify | [lptest-community-website](https://github.com/Fakhripm/lptest-community-website) | [NEXT-GEN-PROGRAMMING/community-website](https://github.com/NEXT-GEN-PROGRAMMING/community-website) | MIT | Node (unpinned: 22) | pnpm 11, pnpm 10 | In progress | Deploying again on the new rules. Security commits |
| pnpm 8 lock file | [lptest-TiantianFundApi](https://github.com/Fakhripm/lptest-TiantianFundApi) | [kouchao/TiantianFundApi](https://github.com/kouchao/TiantianFundApi) | MIT | Node (unpinned: 22) | pnpm 8 | Live | Installs with pnpm 8. 1 change and 16 security commits |
| pnpm 8 lock file | [lptest-ipdb-API](https://github.com/Fakhripm/lptest-ipdb-API) | [metowolf/ipdb-API](https://github.com/metowolf/ipdb-API) | MIT | Node (unpinned: 22) | pnpm 8 | Live | 1 Launchpad commit |
| pnpm 8 lock file | [lptest-fastify-jwt-typescript](https://github.com/Fakhripm/lptest-fastify-jwt-typescript) | [thomasjonstrup/fastify-jwt-typescript](https://github.com/thomasjonstrup/fastify-jwt-typescript) | MIT | Node (unpinned: 22) | pnpm 8 | Live | Installs with pnpm 8. Listen fix and security pins committed |
| pnpm 7 lock file | [lptest-Habits-Server](https://github.com/Fakhripm/lptest-Habits-Server) | [GabrielGuedess/Habits-Server](https://github.com/GabrielGuedess/Habits-Server) | MIT | Node (unpinned: 22) | pnpm 7 | In progress | Built and started; the live check timed out while the local stack restarted |
| pnpm 7 lock file | [lptest-nextjs-stripe-starter](https://github.com/Fakhripm/lptest-nextjs-stripe-starter) | [nhost/nextjs-stripe-starter](https://github.com/nhost/nextjs-stripe-starter) | MIT | Node (unpinned: 22) | pnpm 7 | Live | Installs with pnpm 7. 14 Launchpad commits |

## How a copy was made

1. The upstream's default branch was copied with its whole history, as `main`.
2. [gitleaks](https://github.com/gitleaks/gitleaks) v8.21.2 scanned the history before publishing. A repo whose findings were all sample values (example env files, mocks, tests, docs), which the upstream already publishes, was published. A repo with a finding in a real env file was replaced by another app.
3. The upstream's GitHub Actions workflows were removed, and Actions is switched off on every copy.
4. Each app was deployed on Launchpad's local stack. Settings Launchpad asked the owner for were answered with the values in the app's own example files, or a placeholder where the file has none. Every security fix Launchpad offered was accepted. Each change Launchpad made to the code (security fixes, its repairs, and build fixes for defects in the upstream app) was committed to the copy with Launchpad's own message, and each touched lock file was brought up to date by the package manager that wrote it. Build fixes that would only hide a Launchpad bug were not accepted: the bug was fixed in Launchpad's rules instead.

## Left out

These apps were tested before but have no licence file, so they cannot be published as copies: dhatGuy/PERN-Store, danieljecu/todos_app, vwcwong/pern-stack-template, Yogndrr/MERN-School-Management-System, vercel/nextjs-postgres-auth-starter and TomDoesTech/fastify-prisma-rest-api.

cefjoeii/mern-crud builds its React app into the Express server's `public/` folder. Launchpad does not deploy that layout yet.
