# Naming Convention Reference

> **Core principle:** Every name reads left to right — largest scope to smallest detail.
> Use only the segments you need. Never pad with empty segments.

---

## Table of Contents

1. [Naming Structure](#1-naming-structure)
2. [Capitalization Rules](#2-capitalization-rules)
3. [Prefixes & Suffixes](#3-prefixes--suffixes)
4. [Sorting & Grouping](#4-sorting--grouping)
5. [Standard Abbreviations](#5-standard-abbreviations)

---

## 1. Naming Structure

### Core Formula

```
[domain] + [context] + [entity] + [descriptor] + [variant] + [version] + [date]
```

| Segment | Purpose | Stability |
|---|---|---|
| `domain` | Highest-level bucket (project, team, system) | Most stable |
| `context` | Sub-area within the domain | Stable |
| `entity` | The specific thing being named | Moderate |
| `descriptor` | Qualifier — narrows the entity | Moderate |
| `variant` | Period, state, size, locale | Volatile |
| `[version]` | Optional — `v1`, `v1.2`, `v2` | Volatile |
| `[date]` | Optional — `yyyy-mm-dd` prefix for logs/snapshots | Most volatile |

### Separator by Context

| Context | Style | Separator | Example |
|---|---|---|---|
| Variables, functions, JSON keys | camelCase | none (case shift) | `userAuthToken` |
| Classes, types, interfaces | PascalCase | none (case shift) | `UserAuthService` |
| Files, folders, CSS | kebab-case | `-` hyphen | `user-auth-service.ts` |
| Database tables, columns | snake_case | `_` underscore | `user_auth_tokens` |
| Env vars, constants | SCREAMING_SNAKE | `_` underscore | `AUTH_JWT_SECRET` |

### Date Prefix (when chronological sort = intended sort)

```
yyyy-mm-dd_domain-context-entity
```

```
2026-04-22_finance-report-q1.xlsx
2026-01-15_client-acme-kickoff.md
```

> Use date prefix **only** for logs, meeting notes, and time-bound snapshots.
> For everything else, date trails after the name.

### Version Suffix

```
name-v{N}          →  brand-logo-v2.svg
name-v{N}.{N}      →  api-schema-v1.3.json
```

> Never use `final`, `new`, `updated`, `latest`, or `copy` as versions. Always `v1`, `v2`, `v1.2`.

---

## 2. Capitalization Rules

### camelCase — Code variables & functions

**Rule:** First word all lowercase. Every subsequent word — capitalize the first letter only.

```
"user authentication token"  →  userAuthenticationToken
"fetch user profile"         →  fetchUserProfile
"is order complete"          →  isOrderComplete
```

### PascalCase — Classes, types, interfaces, components

**Rule:** Every word — capitalize the first letter. Same as camelCase but the first word also gets a capital.

```
"user authentication service"  →  UserAuthenticationService
"order summary card"           →  OrderSummaryCard
"api response handler"         →  ApiResponseHandler
```

### kebab-case — Files, folders, CSS

**Rule:** All letters lowercase always. Spaces replaced with hyphens. No capitals anywhere, ever.

```
"User Authentication Service"  →  user-authentication-service.ts
"Order Summary Card"           →  order-summary-card.tsx
"color brand primary"          →  color-brand-primary
```

### snake_case — Database, SQL

**Rule:** All letters lowercase always. Spaces replaced with underscores.

```
"order total amount USD"  →  order_total_amount_usd
"created at timestamp"    →  created_at
"is email verified"       →  is_email_verified
```

### SCREAMING_SNAKE — Env vars, constants

**Rule:** All letters UPPERCASE always. Spaces replaced with underscores.

```
"database connection url"  →  DATABASE_CONNECTION_URL
"auth jwt secret key"      →  AUTH_JWT_SECRET_KEY
"max retry count"          →  MAX_RETRY_COUNT
```

### Acronyms (API, URL, ID, UUID...)

Treat the acronym as a single word. Capitalize only the first letter where a capital is needed — never break an acronym into mixed caps.

| Case | Leading word | Middle/end word |
|---|---|---|
| camelCase | `apiResponse` | `parseApiResponse` |
| PascalCase | `ApiResponseHandler` | `ParseApiResponse` |
| kebab-case | `api-response-handler` | `api-response-handler` |
| snake_case | `api_response_handler` | `api_response_handler` |
| SCREAMING | `API_RESPONSE_HANDLER` | `API_RESPONSE_HANDLER` |

> Never write `APIResponse`, `URLParser`, or `userID` — always `ApiResponse`, `UrlParser`, `userId`.

---

## 3. Prefixes & Suffixes

### When to use

- **Use** when removing the prefix/suffix would cause ambiguity
- **Use** when scanning a flat list — prefixes/suffixes let you filter by role at a glance
- **Avoid** when the name is already self-explanatory
- **Avoid** redundant suffixes if the folder already communicates the type
- **Never use** `Data`, `Info`, `Object`, `Stuff` as suffixes — they add no meaning

---

### Code — Boolean prefixes

Always prefix booleans. The prefix makes intent obvious without reading type annotations.

| Prefix | Meaning | Example |
|---|---|---|
| `is` | current state | `isLoggedIn`, `isVisible` |
| `has` | possession / existence | `hasError`, `hasPermission` |
| `can` | capability / permission | `canEdit`, `canDelete` |
| `should` | recommendation / flag | `shouldRefetch`, `shouldRedirect` |
| `was` | past state | `wasSubmitted`, `wasVisited` |

---

### Code — Function prefixes (verb-first always)

| Prefix | Meaning | Example |
|---|---|---|
| `get` | retrieve (sync) | `getUserById` |
| `fetch` | retrieve (async / network) | `fetchOrderList` |
| `set` | assign a value | `setActiveUser` |
| `update` | modify existing | `updateUserEmail` |
| `create` / `add` | make new | `createOrder`, `addItem` |
| `delete` / `remove` | destroy / detach | `deleteAccount`, `removeItem` |
| `handle` | event handler | `handleFormSubmit` |
| `parse` / `format` | transform data | `parseDate`, `formatCurrency` |
| `validate` / `check` | test a condition | `validateEmail`, `checkPermission` |
| `init` / `reset` | setup / clear | `initDashboard`, `resetForm` |
| `on` | event callback prop | `onClick`, `onSubmit` |

---

### Code — Class & type suffixes (PascalCase)

| Suffix | When to use | Example |
|---|---|---|
| `Service` | business logic / data access | `UserAuthService` |
| `Controller` | handles HTTP requests | `OrderController` |
| `Handler` | processes an event or command | `PaymentWebhookHandler` |
| `Manager` | orchestrates multiple services | `SessionManager` |
| `Repository` | data storage abstraction | `UserRepository` |
| `Factory` | creates instances of objects | `NotificationFactory` |
| `Provider` | supplies data/context | `ThemeProvider`, `AuthProvider` |
| `Error` | custom error classes | `AuthenticationError` |
| `Config` | configuration object | `DatabaseConfig` |

---

### File — dot-separated type suffix (kebab-case)

```
domain-context.type.ext
user-auth.service.ts
order-summary.component.tsx
```

| Suffix | Meaning | Example |
|---|---|---|
| `.service.ts` | business logic | `user-auth.service.ts` |
| `.controller.ts` | route handler | `order.controller.ts` |
| `.component.tsx` | UI component | `nav-bar.component.tsx` |
| `.hook.ts` | custom hook | `use-auth.hook.ts` |
| `.util.ts` | pure helper functions | `date.util.ts` |
| `.types.ts` | type definitions only | `user.types.ts` |
| `.config.ts` | configuration | `database.config.ts` |
| `.test.ts` | unit / integration tests | `user-auth.service.test.ts` |
| `.spec.ts` | BDD-style tests | `order.spec.ts` |
| `.mock.ts` | mock / stub data | `user.mock.ts` |
| `.schema.ts` | validation schema | `login.schema.ts` |
| `.model.ts` | data model / ORM entity | `user.model.ts` |

---

### Database — column suffixes (snake_case)

| Suffix | Meaning | Example |
|---|---|---|
| `_id` | primary or foreign key | `user_id`, `order_id` |
| `_at` | timestamp (when it happened) | `created_at`, `deleted_at` |
| `_on` | date only (no time) | `due_on`, `published_on` |
| `_count` | integer count | `retry_count`, `item_count` |
| `_total` | summed numeric value | `order_total`, `tax_total` |
| `_url` | web address | `avatar_url`, `redirect_uri` |
| `_hash` | hashed value | `password_hash` |
| `_json` | raw JSON blob column | `metadata_json` |
| `_usd` / `_eur` | money with currency unit | `price_usd`, `fee_eur` |
| `is_` | boolean (prefix, not suffix) | `is_active`, `is_verified` |

---

### Git branch prefixes

```
type/description-in-kebab-case
feat/user-oauth-login
fix/order-total-rounding
```

| Prefix | When | Example |
|---|---|---|
| `feat/` | new feature | `feat/user-oauth-login` |
| `fix/` | bug fix | `fix/order-total-rounding` |
| `hotfix/` | urgent production fix | `hotfix/payment-timeout` |
| `chore/` | maintenance, deps, config | `chore/upgrade-node-20` |
| `refactor/` | restructure, no behavior change | `refactor/auth-service` |
| `docs/` | documentation only | `docs/api-readme-update` |
| `release/` | release preparation | `release/v2.4.0` |
| `test/` | adding or fixing tests only | `test/user-service-coverage` |

---

## 4. Sorting & Grouping

### Sort order rule — stable → volatile

Names sort correctly alphabetically only when the most stable, broadest identifier leads.

```
domain → category → entity → variant → [version] → [date]
```

| Position | What goes here | Example |
|---|---|---|
| 1 — most stable | Domain / project | `finance-` |
| 2 | Category / type | `finance-report-` |
| 3 | Entity / subject | `finance-report-revenue` |
| 4 | Variant / qualifier | `finance-report-revenue-q1` |
| 5 — most volatile | Version or date | `finance-report-revenue-q1-v2` |

### What this looks like sorted

```
❌ Unsortable                       ✅ Self-sorting
────────────────────────────────    ────────────────────────────────────
q1-revenue-finance.xlsx             finance-budget-2026-v1.xlsx
budget2026-hr.xlsx                  finance-report-expenses-q1.xlsx
final-report-v2.xlsx                finance-report-revenue-q1.xlsx
march-expenses.xlsx                 finance-report-revenue-q2.xlsx
revenue-q2-final.xlsx               hr-policy-onboarding-v2.xlsx
```

### When date leads vs trails

| Scenario | Pattern | Reason |
|---|---|---|
| Logs, meeting notes, snapshots | `yyyy-mm-dd_name` | Chronological sort = intended sort |
| Reports, documents, assets | `name-qualifier-v1` | Topic sort first, date trails |

### Standard variant keywords

Always pick one form and never mix synonyms — `q1` and `quarter1` won't sort together.

| Category | Use this | Never use |
|---|---|---|
| Quarters | `q1` `q2` `q3` `q4` | `quarter1`, `Q1`, `qtr1` |
| Months | `jan` `feb` `mar` ... `dec` | `january`, `01`, `month1` |
| Versions | `v1` `v1.2` `v2` | `final`, `new`, `updated`, `latest` |
| States | `draft` `review` `approved` `archived` | `wip`, `temp`, `old`, `bak` |
| Size | `sm` `md` `lg` `xl` | `small`, `big`, `large` |
| Breakpoint | `mobile` `desktop` | `phone`, `computer`, `web` |
| Theme | `dark` `light` `primary` `secondary` | `black`, `white`, `main`, `alt` |
| Environment | `dev` `stg` `prod` | `development`, `local`, `live` |
| Locale | `en` `es` `fr` (ISO 639-1) | `english`, `spanish`, `lang-en` |

### Folders vs name prefixes

| Use folders when... | Use name prefix when... |
|---|---|
| A group has 10+ files | Files from multiple domains live together |
| Files are only accessed together | It's a flat shared drive or asset library |
| The domain is a whole project/team | You need to search across groups at once |
| You need permission control per group | The group is small (2–5 files) |

> **Best practice:** Use both together. Folder = coarse grouping, name prefix = fine grouping within the folder. Never rely on folders alone — a file moved out loses its meaning.

---

## 5. Standard Abbreviations

> Rules: 2–5 characters max. All lowercase (except SCREAMING_SNAKE context). Never abbreviate when it hurts clarity.

---

### Software / Code

| Abbr. | Meaning | Example use |
|---|---|---|
| `api` | application programming interface | `userApi`, `auth-api.ts` |
| `app` | application | `app-config.ts`, `myApp` |
| `auth` | authentication / authorization | `authService`, `user-auth.ts` |
| `btn` | button | `btn-primary`, `submitBtn` |
| `cfg` | configuration | `db-cfg.ts`, `appCfg` |
| `cli` | command line interface | `cli-tool`, `runCli()` |
| `comp` | component | `NavComp`, `user-comp.tsx` |
| `ctx` | context | `authCtx`, `AppCtx` |
| `db` | database | `dbConfig`, `db-migrate.ts` |
| `err` | error | `errHandler`, `onErr` |
| `fn` | function | `helperFn`, `callbackFn` |
| `id` | identifier | `userId`, `order_id` |
| `lib` | library | `lib/utils`, `libHelpers` |
| `mgr` | manager | `sessionMgr`, `cacheMgr` |
| `mw` | middleware | `auth-mw.ts`, `logMw` |
| `msg` | message | `errMsg`, `successMsg` |
| `param` | parameter | `queryParam`, `routeParam` |
| `pkg` | package | `pkg.json`, `corePkg` |
| `repo` | repository | `userRepo`, `order-repo.ts` |
| `req` | request | `req.body`, `httpReq` |
| `res` | response | `res.json()`, `apiRes` |
| `svc` | service | `authSvc`, `user-svc.ts` |
| `tmp` | temporary | `tmpFile`, `temp-cache` |
| `util` | utility | `dateUtil`, `string-util.ts` |
| `val` | value / validate | `inputVal`, `validateFn` |
| `var` | variable | `envVar`, `configVar` |

---

### Data / Database

| Abbr. | Meaning | Example use |
|---|---|---|
| `agg` | aggregate | `agg_sales_total` |
| `col` | column | `col_user_id` |
| `dim` | dimension (data warehouse) | `dim_product`, `dim_date` |
| `etl` | extract transform load | `etl_orders_daily` |
| `fact` | fact table (data warehouse) | `fact_sales`, `fact_events` |
| `fk` | foreign key | `fk_user_id` |
| `idx` | index | `idx_user_email` |
| `pk` | primary key | `pk_order_id` |
| `proc` | stored procedure | `proc_get_user` |
| `qry` | query | `qry_active_users` |
| `sp` | stored procedure (alt) | `sp_update_order` |
| `stg` | staging | `stg_raw_events` |
| `tbl` | table | `tbl_users`, `tbl_orders` |
| `tmp` | temporary table | `tmp_calc_results` |
| `view` | database view | `view_user_summary` |

---

### Business / Finance

| Abbr. | Meaning | Example use |
|---|---|---|
| `acct` | account | `acct-payable`, `acctMgr` |
| `addr` | address | `addr_shipping`, `billingAddr` |
| `amt` | amount | `amt_due`, `paymentAmt` |
| `arr` | annual recurring revenue | `finance-report-arr` |
| `b2b` | business to business | `b2b-portal`, `b2bClient` |
| `b2c` | business to consumer | `b2c-campaign` |
| `bal` | balance | `bal_outstanding` |
| `client` | client / customer | `client-acme`, `clientId` |
| `crm` | customer relationship mgmt | `crm-sync-contacts` |
| `dept` | department | `dept_finance`, `deptCode` |
| `doc` | document | `doc-template-v1` |
| `est` | estimate | `proj-est-q2.xlsx` |
| `exp` | expenses / expenditure | `finance-report-exp` |
| `inv` | invoice | `inv-2026-04-acme.pdf` |
| `kpi` | key performance indicator | `kpi-dashboard` |
| `mgmt` | management | `proj-mgmt`, `taskMgmt` |
| `mrr` | monthly recurring revenue | `finance-report-mrr` |
| `org` | organization | `org-chart`, `orgId` |
| `po` | purchase order | `po-2026-001.pdf` |
| `proj` | project | `proj-alpha`, `projId` |
| `prop` | proposal | `prop-acme-q2-v1.docx` |
| `ref` | reference | `refNum`, `ref_id` |
| `rev` | revenue / review | `finance-report-rev` |
| `roi` | return on investment | `roi-analysis-q1` |
| `sla` | service level agreement | `sla-doc-v2.pdf` |
| `stmt` | statement | `stmt-finance-jan` |
| `usr` | user | `usrProfile`, `usr_id` |
| `vnd` | vendor | `vnd-acme`, `vndList` |

---

### Design / UI

| Abbr. | Meaning | Example use |
|---|---|---|
| `bg` | background | `bg-dark.jpg`, `bgColor` |
| `btn` | button | `btn-primary.svg` |
| `clr` | color | `clr-brand-primary` |
| `cta` | call to action | `cta-banner-v2` |
| `fnt` | font / typeface | `fnt-heading`, `fntSize` |
| `ic` / `ico` | icon | `ic-arrow-right.svg` |
| `img` | image | `img-hero-desktop.jpg` |
| `lyt` | layout | `lyt-dashboard` |
| `mb` | mobile | `hero-bg-mb.jpg` |
| `nav` | navigation | `nav-bar`, `navItem` |
| `pd` | padding | `pd-lg`, `padTop` |
| `px` | pixel | `icon-24px.svg` |
| `sp` | spacing | `sp-component-md` |
| `sz` | size / sizing | `sz-lg`, `btnSz` |
| `thm` | theme | `thm-dark`, `thmProvider` |
| `tok` | design token | `tok-color-primary` |
| `ui` | user interface | `ui-components/` |
| `ux` | user experience | `ux-research-q1` |
| `wf` | wireframe | `wf-dashboard-v1.fig` |

---

### DevOps / Infrastructure

| Abbr. | Meaning | Example use |
|---|---|---|
| `aws` | amazon web services | `aws-deploy.yml` |
| `cfg` | configuration | `cfg-nginx.conf` |
| `ci` | continuous integration | `ci-pipeline.yml` |
| `cd` | continuous deployment | `cd-workflow.yml` |
| `cicd` | ci/cd pipeline | `cicd-config.yml` |
| `ctr` | container | `ctr-api`, `docker-ctr` |
| `dns` | domain name system | `dns-config.yml` |
| `env` | environment | `env-prod`, `.env.staging` |
| `gcp` | google cloud platform | `gcp-deploy.yml` |
| `infra` | infrastructure | `infra-setup.tf` |
| `k8s` | kubernetes | `k8s-deployment.yml` |
| `lb` | load balancer | `lb-config.yml` |
| `log` | log / logging | `log-error.txt`, `logSvc` |
| `mon` | monitoring | `mon-dashboard` |
| `net` | network | `net-policy.yml` |
| `prod` | production | `env-prod`, `prod-deploy` |
| `sec` | security | `sec-policy.md` |
| `stg` | staging | `env-stg`, `stg-deploy` |
| `svc` | service | `svc-auth.yml` |
| `tf` | terraform | `infra-main.tf` |
| `vm` | virtual machine | `vm-worker-01` |

---

### Time / Dates / Periods

| Abbr. | Meaning | Example use |
|---|---|---|
| `q1`–`q4` | quarter 1 through 4 | `finance-report-q1` |
| `h1` / `h2` | half year (H1 = jan–jun) | `finance-report-h1` |
| `jan`–`dec` | month abbreviations | `2026-01_report` |
| `wk` | week number | `wk-14-report` |
| `yr` | year | `budget-yr-2026` |
| `ann` | annual | `finance-report-ann` |
| `eod` | end of day | `eod-summary` |
| `eom` | end of month | `eom-finance-stmt` |
| `eoy` | end of year | `eoy-review-2026` |
| `daily` | daily cadence | `etl_orders_daily` |
| `weekly` | weekly cadence | `report-sales-weekly` |
| `monthly` | monthly cadence | `etl_revenue_monthly` |
| `mon`–`fri` | day of week | `mon-standup`, `fri-review` |

---

### Files / Folders / Projects

| Abbr. | Meaning | Example use |
|---|---|---|
| `arch` | archive | `arch-2024-projects/` |
| `assets` | static assets folder | `assets/icons/` |
| `bak` | backup | `db-bak-2026-04-22` |
| `bin` | binary / build output | `bin/`, `dist/bin` |
| `build` | build output folder | `build/`, `dist/` |
| `cache` | cache folder | `.cache/`, `cache-dir` |
| `dist` | distribution build | `dist/`, `dist-prod` |
| `docs` | documentation | `docs/`, `project-docs` |
| `draft` | draft / work in progress | `proposal-draft-v1` |
| `lib` | library / shared code | `lib/`, `shared-lib` |
| `logs` | log files folder | `logs/error-2026.log` |
| `out` | output folder | `out/`, `reports-out` |
| `pub` | public folder | `pub/`, `public/` |
| `ref` | reference material | `ref-architecture.pdf` |
| `src` | source code folder | `src/`, `src/components` |
| `templates` | template files | `templates/invoice.docx` |
| `tests` | test files folder | `tests/`, `__tests__/` |
| `tmp` | temporary files | `tmp/`, `.tmp-cache` |
| `vendor` | third-party code | `vendor/`, `vendor-libs` |

---

### Custom Abbreviations

> Add your own below. Follow the same rules: 2–5 characters, lowercase, no ambiguity.

| Abbr. | Meaning | Domain | Example use |
|---|---|---|---|
| | | | |
| | | | |
| | | | |

---

*Last updated: 2026-04-22 — v1.0*
