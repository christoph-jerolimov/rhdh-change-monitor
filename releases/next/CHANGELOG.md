# RHDH Release next changelog

Changes between Backstage 1.54.7 (RHDH 2.1) and Backstage 1.57.0-next.0 (RHDH next) — 6 added, 0 removed, 203 upgraded, 7 unchanged packages.

## Summary

- [Newly added packages](#newly-added-packages): 6 packages
- [Breaking changes](#breaking-changes): 15 packages
- [Major version bumps](#major-version-bumps): 2 packages
- [0.x minor version bumps](#0x-minor-version-bumps): 5 packages
- [0.0.x patch version bumps](#00x-patch-version-bumps): 3 packages
- [0.x patch version bumps](#0x-patch-version-bumps): 80 packages
- [Other minor version bumps](#other-minor-version-bumps): 9 packages
- [Other patch version bumps](#other-patch-version-bumps): 15 packages
- [Excluded dependency updates](#excluded-dependency-updates): 74 packages

## Table of contents

- [Newly added packages](#newly-added-packages)
  - [`@backstage/cli-module-catalog` (new, 0.2.1-next.0)](#backstagecli-module-catalog-new-021-next0)
  - [`@backstage/cli-module-package-manager-yarn` (new, 0.1.5-next.0)](#backstagecli-module-package-manager-yarn-new-015-next0)
  - [`@backstage/cli-module-scaffolder` (new, 0.2.1-next.0)](#backstagecli-module-scaffolder-new-021-next0)
  - [`@backstage/cli-module-search` (new, 0.2.1-next.0)](#backstagecli-module-search-new-021-next0)
  - [`@backstage/plugin-scaffolder-backend-module-workspace-database` (new, 0.1.2-next.0)](#backstageplugin-scaffolder-backend-module-workspace-database-new-012-next0)
  - [`@backstage/plugin-techdocs-backend-module-zensical` (new, 0.1.0-next.0)](#backstageplugin-techdocs-backend-module-zensical-new-010-next0)
- [Breaking changes](#breaking-changes)
  - [`@backstage/backend-plugin-api` (1.10.0 → 1.11.1-next.0)](#backstagebackend-plugin-api-1100--1111-next0)
  - [`@backstage/connections` (0.3.0 → 0.4.1)](#backstageconnections-030--041)
  - [`@backstage/filter-predicates` (0.1.4 → 0.2.0)](#backstagefilter-predicates-014--020)
  - [`@backstage/frontend-test-utils` (0.6.3 → 0.7.0-next.0)](#backstagefrontend-test-utils-063--070-next0)
  - [`@backstage/plugin-auth-backend-module-atlassian-provider` (0.4.18 → 0.5.1-next.0)](#backstageplugin-auth-backend-module-atlassian-provider-0418--051-next0)
  - [`@backstage/plugin-auth-backend-module-cloudflare-access-provider` (0.4.18 → 0.5.2-next.0)](#backstageplugin-auth-backend-module-cloudflare-access-provider-0418--052-next0)
  - [`@backstage/plugin-catalog-backend` (3.9.1 → 4.0.3-next.0)](#backstageplugin-catalog-backend-391--403-next0)
  - [`@backstage/plugin-catalog-backend-module-incremental-ingestion` (0.7.15 → 0.9.1-next.0)](#backstageplugin-catalog-backend-module-incremental-ingestion-0715--091-next0)
  - [`@backstage/plugin-kubernetes-react` (0.5.23 → 0.6.2-next.0)](#backstageplugin-kubernetes-react-0523--062-next0)
  - [`@backstage/plugin-scaffolder-backend-module-gcp` (0.2.24 → 0.3.0-next.0)](#backstageplugin-scaffolder-backend-module-gcp-0224--030-next0)
  - [`@backstage/plugin-scaffolder-backend-module-github` (0.9.13 → 0.10.2-next.0)](#backstageplugin-scaffolder-backend-module-github-0913--0102-next0)
  - [`@backstage/plugin-scaffolder-backend-module-sentry` (0.3.7 → 0.4.2-next.0)](#backstageplugin-scaffolder-backend-module-sentry-037--042-next0)
  - [`@backstage/plugin-search-backend-module-elasticsearch` (1.8.7 → 2.0.2-next.0)](#backstageplugin-search-backend-module-elasticsearch-187--202-next0)
  - [`@backstage/plugin-techdocs-node` (1.15.4 → 2.2.0-next.0)](#backstageplugin-techdocs-node-1154--220-next0)
  - [`@backstage/ui` (0.17.1 → 0.19.0)](#backstageui-0171--0190)
- [Major version bumps](#major-version-bumps)
  - [`@backstage/plugin-catalog-react` (3.2.2 → 4.0.0-next.0)](#backstageplugin-catalog-react-322--400-next0)
  - [`@backstage/plugin-scaffolder-react` (2.0.3 → 3.0.0-next.0)](#backstageplugin-scaffolder-react-203--300-next0)
- [0.x minor version bumps](#0x-minor-version-bumps)
  - [`@backstage/backend-defaults` (0.17.8 → 0.18.2-next.0)](#backstagebackend-defaults-0178--0182-next0)
  - [`@backstage/plugin-catalog-backend-module-github` (0.13.5 → 0.14.2-next.0)](#backstageplugin-catalog-backend-module-github-0135--0142-next0)
  - [`@backstage/plugin-notifications` (0.5.20 → 0.6.2-next.0)](#backstageplugin-notifications-0520--062-next0)
  - [`@backstage/plugin-org` (0.7.8 → 0.8.1-next.0)](#backstageplugin-org-078--081-next0)
  - [`@backstage/plugin-scaffolder-backend-module-gitlab` (0.11.10 → 0.12.2-next.0)](#backstageplugin-scaffolder-backend-module-gitlab-01110--0122-next0)
- [0.0.x patch version bumps](#00x-patch-version-bumps)
  - [`@backstage/plugin-kubernetes-cluster` (0.0.40 → 0.0.43-next.0)](#backstageplugin-kubernetes-cluster-0040--0043-next0)
  - [`@backstage/plugin-signals` (0.0.34 → 0.0.37-next.0)](#backstageplugin-signals-0034--0037-next0)
  - [`@backstage/release-manifests` (0.0.14 → 0.0.15)](#backstagerelease-manifests-0014--0015)
- [0.x patch version bumps](#0x-patch-version-bumps)
  - [`@backstage/backend-dynamic-feature-service` (0.8.6 → 0.8.9-next.0)](#backstagebackend-dynamic-feature-service-086--089-next0)
  - [`@backstage/backend-openapi-utils` (0.7.1 → 0.7.4-next.0)](#backstagebackend-openapi-utils-071--074-next0)
  - [`@backstage/cli` (0.36.5 → 0.36.8-next.0)](#backstagecli-0365--0368-next0)
  - [`@backstage/cli-common` (0.3.0 → 0.3.2)](#backstagecli-common-030--032)
  - [`@backstage/cli-defaults` (0.1.5 → 0.1.8-next.0)](#backstagecli-defaults-015--018-next0)
  - [`@backstage/cli-module-actions` (0.1.3 → 0.1.5-next.0)](#backstagecli-module-actions-013--015-next0)
  - [`@backstage/cli-module-auth` (0.1.4 → 0.1.6-next.0)](#backstagecli-module-auth-014--016-next0)
  - [`@backstage/cli-module-build` (0.1.7 → 0.1.10-next.0)](#backstagecli-module-build-017--0110-next0)
  - [`@backstage/cli-module-maintenance` (0.1.4 → 0.1.7-next.0)](#backstagecli-module-maintenance-014--017-next0)
  - [`@backstage/cli-module-new` (0.1.6 → 0.1.9-next.0)](#backstagecli-module-new-016--019-next0)
  - [`@backstage/cli-module-test-jest` (0.1.5 → 0.1.8-next.0)](#backstagecli-module-test-jest-015--018-next0)
  - [`@backstage/cli-node` (0.3.4 → 0.3.6-next.0)](#backstagecli-node-034--036-next0)
  - [`@backstage/core-compat-api` (0.5.14 → 0.5.17-next.0)](#backstagecore-compat-api-0514--0517-next0)
  - [`@backstage/core-components` (0.18.13 → 0.18.16-next.0)](#backstagecore-components-01813--01816-next0)
  - [`@backstage/create-app` (0.9.1 → 0.9.4-next.0)](#backstagecreate-app-091--094-next0)
  - [`@backstage/eslint-plugin` (0.3.2 → 0.3.4-next.0)](#backstageeslint-plugin-032--034-next0)
  - [`@backstage/frontend-app-api` (0.16.7 → 0.16.10-next.0)](#backstagefrontend-app-api-0167--01610-next0)
  - [`@backstage/frontend-dynamic-feature-loader` (0.1.15 → 0.1.18-next.0)](#backstagefrontend-dynamic-feature-loader-0115--0118-next0)
  - [`@backstage/frontend-plugin-api` (0.18.0 → 0.18.3-next.0)](#backstagefrontend-plugin-api-0180--0183-next0)
  - [`@backstage/module-federation-common` (0.1.4 → 0.1.6)](#backstagemodule-federation-common-014--016)
  - [`@backstage/plugin-api-docs` (0.14.4 → 0.14.7-next.0)](#backstageplugin-api-docs-0144--0147-next0)
  - [`@backstage/plugin-app` (0.5.2 → 0.5.5-next.0)](#backstageplugin-app-052--055-next0)
  - [`@backstage/plugin-app-backend` (0.5.17 → 0.5.20-next.0)](#backstageplugin-app-backend-0517--0520-next0)
  - [`@backstage/plugin-app-module-user-settings` (0.1.1 → 0.1.4-next.0)](#backstageplugin-app-module-user-settings-011--014-next0)
  - [`@backstage/plugin-app-react` (0.2.6 → 0.2.9-next.0)](#backstageplugin-app-react-026--029-next0)
  - [`@backstage/plugin-app-visualizer` (0.2.7 → 0.2.10-next.0)](#backstageplugin-app-visualizer-027--0210-next0)
  - [`@backstage/plugin-auth-backend` (0.30.0 → 0.30.3-next.0)](#backstageplugin-auth-backend-0300--0303-next0)
  - [`@backstage/plugin-auth-backend-module-auth0-provider` (0.4.4 → 0.4.7-next.0)](#backstageplugin-auth-backend-module-auth0-provider-044--047-next0)
  - [`@backstage/plugin-auth-backend-module-aws-alb-provider` (0.4.19 → 0.4.22-next.0)](#backstageplugin-auth-backend-module-aws-alb-provider-0419--0422-next0)
  - [`@backstage/plugin-auth-backend-module-azure-easyauth-provider` (0.2.23 → 0.2.26-next.0)](#backstageplugin-auth-backend-module-azure-easyauth-provider-0223--0226-next0)
  - [`@backstage/plugin-auth-backend-module-gcp-iap-provider` (0.4.18 → 0.4.21-next.0)](#backstageplugin-auth-backend-module-gcp-iap-provider-0418--0421-next0)
  - [`@backstage/plugin-auth-backend-module-github-provider` (0.5.6 → 0.5.9-next.0)](#backstageplugin-auth-backend-module-github-provider-056--059-next0)
  - [`@backstage/plugin-auth-backend-module-guest-provider` (0.2.22 → 0.2.25-next.0)](#backstageplugin-auth-backend-module-guest-provider-0222--0225-next0)
  - [`@backstage/plugin-auth-backend-module-microsoft-provider` (0.3.18 → 0.3.21-next.0)](#backstageplugin-auth-backend-module-microsoft-provider-0318--0321-next0)
  - [`@backstage/plugin-auth-backend-module-oauth2-proxy-provider` (0.3.2 → 0.3.5-next.0)](#backstageplugin-auth-backend-module-oauth2-proxy-provider-032--035-next0)
  - [`@backstage/plugin-auth-backend-module-oidc-provider` (0.4.20 → 0.4.23-next.0)](#backstageplugin-auth-backend-module-oidc-provider-0420--0423-next0)
  - [`@backstage/plugin-auth-backend-module-pinniped-provider` (0.3.17 → 0.3.20-next.0)](#backstageplugin-auth-backend-module-pinniped-provider-0317--0320-next0)
  - [`@backstage/plugin-auth-backend-module-vmware-cloud-provider` (0.5.17 → 0.5.20-next.0)](#backstageplugin-auth-backend-module-vmware-cloud-provider-0517--0520-next0)
  - [`@backstage/plugin-auth-node` (0.7.5 → 0.7.8-next.0)](#backstageplugin-auth-node-075--078-next0)
  - [`@backstage/plugin-bitbucket-cloud-common` (0.3.12 → 0.3.14)](#backstageplugin-bitbucket-cloud-common-0312--0314)
  - [`@backstage/plugin-catalog-backend-module-aws` (0.4.27 → 0.4.30-next.0)](#backstageplugin-catalog-backend-module-aws-0427--0430-next0)
  - [`@backstage/plugin-catalog-backend-module-azure` (0.3.21 → 0.3.24-next.0)](#backstageplugin-catalog-backend-module-azure-0321--0324-next0)
  - [`@backstage/plugin-catalog-backend-module-bitbucket-server` (0.5.14 → 0.5.17-next.0)](#backstageplugin-catalog-backend-module-bitbucket-server-0514--0517-next0)
  - [`@backstage/plugin-catalog-backend-module-gitea` (0.1.15 → 0.1.18-next.0)](#backstageplugin-catalog-backend-module-gitea-0115--0118-next0)
  - [`@backstage/plugin-catalog-backend-module-gitlab` (0.8.7 → 0.8.10-next.0)](#backstageplugin-catalog-backend-module-gitlab-087--0810-next0)
  - [`@backstage/plugin-catalog-backend-module-ldap` (0.12.8 → 0.12.11-next.0)](#backstageplugin-catalog-backend-module-ldap-0128--01211-next0)
  - [`@backstage/plugin-catalog-backend-module-msgraph` (0.10.5 → 0.10.8-next.0)](#backstageplugin-catalog-backend-module-msgraph-0105--0108-next0)
  - [`@backstage/plugin-catalog-backend-module-puppetdb` (0.2.25 → 0.2.28-next.0)](#backstageplugin-catalog-backend-module-puppetdb-0225--0228-next0)
  - [`@backstage/plugin-catalog-backend-module-unprocessed` (0.6.15 → 0.6.18-next.0)](#backstageplugin-catalog-backend-module-unprocessed-0615--0618-next0)
  - [`@backstage/plugin-catalog-graph` (0.6.7 → 0.6.10-next.0)](#backstageplugin-catalog-graph-067--0610-next0)
  - [`@backstage/plugin-catalog-import` (0.13.17 → 0.13.20-next.0)](#backstageplugin-catalog-import-01317--01320-next0)
  - [`@backstage/plugin-catalog-unprocessed-entities` (0.2.34 → 0.2.37-next.0)](#backstageplugin-catalog-unprocessed-entities-0234--0237-next0)
  - [`@backstage/plugin-devtools` (0.1.42 → 0.1.45-next.0)](#backstageplugin-devtools-0142--0145-next0)
  - [`@backstage/plugin-events-backend` (0.6.5 → 0.6.8-next.0)](#backstageplugin-events-backend-065--068-next0)
  - [`@backstage/plugin-home` (0.9.9 → 0.9.12-next.0)](#backstageplugin-home-099--0912-next0)
  - [`@backstage/plugin-home-react` (0.1.41 → 0.1.44-next.0)](#backstageplugin-home-react-0141--0144-next0)
  - [`@backstage/plugin-kubernetes` (0.12.22 → 0.12.25-next.0)](#backstageplugin-kubernetes-01222--01225-next0)
  - [`@backstage/plugin-kubernetes-backend` (0.21.10 → 0.21.13-next.0)](#backstageplugin-kubernetes-backend-02110--02113-next0)
  - [`@backstage/plugin-kubernetes-common` (0.9.12 → 0.9.15-next.0)](#backstageplugin-kubernetes-common-0912--0915-next0)
  - [`@backstage/plugin-kubernetes-node` (0.4.7 → 0.4.10-next.0)](#backstageplugin-kubernetes-node-047--0410-next0)
  - [`@backstage/plugin-mcp-actions-backend` (0.2.1 → 0.2.4-next.0)](#backstageplugin-mcp-actions-backend-021--024-next0)
  - [`@backstage/plugin-mui-to-bui` (0.2.10 → 0.2.13-next.0)](#backstageplugin-mui-to-bui-0210--0213-next0)
  - [`@backstage/plugin-notifications-backend` (0.6.8 → 0.6.11-next.0)](#backstageplugin-notifications-backend-068--0611-next0)
  - [`@backstage/plugin-notifications-backend-module-email` (0.3.24 → 0.3.27-next.0)](#backstageplugin-notifications-backend-module-email-0324--0327-next0)
  - [`@backstage/plugin-notifications-backend-module-slack` (0.4.5 → 0.4.8-next.0)](#backstageplugin-notifications-backend-module-slack-045--048-next0)
  - [`@backstage/plugin-notifications-node` (0.2.29 → 0.2.32-next.0)](#backstageplugin-notifications-node-0229--0232-next0)
  - [`@backstage/plugin-proxy-backend` (0.6.17 → 0.6.20-next.0)](#backstageplugin-proxy-backend-0617--0620-next0)
  - [`@backstage/plugin-scaffolder-backend-module-azure` (0.2.25 → 0.2.28-next.0)](#backstageplugin-scaffolder-backend-module-azure-0225--0228-next0)
  - [`@backstage/plugin-scaffolder-backend-module-bitbucket-cloud` (0.3.10 → 0.3.13-next.0)](#backstageplugin-scaffolder-backend-module-bitbucket-cloud-0310--0313-next0)
  - [`@backstage/plugin-scaffolder-backend-module-bitbucket-server` (0.2.25 → 0.2.28-next.0)](#backstageplugin-scaffolder-backend-module-bitbucket-server-0225--0228-next0)
  - [`@backstage/plugin-scaffolder-backend-module-confluence-to-markdown` (0.3.25 → 0.3.28-next.0)](#backstageplugin-scaffolder-backend-module-confluence-to-markdown-0325--0328-next0)
  - [`@backstage/plugin-scaffolder-node` (0.13.6 → 0.13.9-next.0)](#backstageplugin-scaffolder-node-0136--0139-next0)
  - [`@backstage/plugin-search-backend-module-catalog` (0.3.18 → 0.3.21-next.0)](#backstageplugin-search-backend-module-catalog-0318--0321-next0)
  - [`@backstage/plugin-search-backend-module-explore` (0.3.17 → 0.3.20-next.0)](#backstageplugin-search-backend-module-explore-0317--0320-next0)
  - [`@backstage/plugin-search-backend-module-pg` (0.5.58 → 0.5.61-next.0)](#backstageplugin-search-backend-module-pg-0558--0561-next0)
  - [`@backstage/plugin-search-backend-module-techdocs` (0.4.17 → 0.4.20-next.0)](#backstageplugin-search-backend-module-techdocs-0417--0420-next0)
  - [`@backstage/plugin-signals-backend` (0.3.18 → 0.3.21-next.0)](#backstageplugin-signals-backend-0318--0321-next0)
  - [`@backstage/plugin-techdocs-common` (0.1.1 → 0.1.2)](#backstageplugin-techdocs-common-011--012)
  - [`@backstage/plugin-user-settings` (0.9.6 → 0.9.9-next.0)](#backstageplugin-user-settings-096--099-next0)
  - [`@backstage/repo-tools` (0.19.0 → 0.19.3-next.0)](#backstagerepo-tools-0190--0193-next0)
- [Other minor version bumps](#other-minor-version-bumps)
  - [`@backstage/backend-app-api` (1.7.3 → 1.9.0-next.0)](#backstagebackend-app-api-173--190-next0)
  - [`@backstage/plugin-catalog-common` (1.1.10 → 1.2.1)](#backstageplugin-catalog-common-1110--121)
  - [`@backstage/plugin-scaffolder` (1.38.2 → 1.41.0-next.0)](#backstageplugin-scaffolder-1382--1410-next0)
  - [`@backstage/plugin-scaffolder-backend` (4.1.0 → 4.2.2-next.0)](#backstageplugin-scaffolder-backend-410--422-next0)
  - [`@backstage/plugin-scaffolder-common` (2.2.3 → 2.3.1)](#backstageplugin-scaffolder-common-223--231)
  - [`@backstage/plugin-techdocs` (1.18.0 → 1.19.1-next.0)](#backstageplugin-techdocs-1180--1191-next0)
  - [`@backstage/plugin-techdocs-backend` (2.2.4 → 2.4.1-next.0)](#backstageplugin-techdocs-backend-224--241-next0)
  - [`@backstage/plugin-techdocs-react` (1.3.14 → 1.4.1-next.0)](#backstageplugin-techdocs-react-1314--141-next0)
  - [`@techdocs/cli` (1.11.4 → 1.14.0-next.0)](#techdocscli-1114--1140-next0)
- [Other patch version bumps](#other-patch-version-bumps)
  - [`@backstage/backend-test-utils` (1.11.6 → 1.11.9-next.0)](#backstagebackend-test-utils-1116--1119-next0)
  - [`@backstage/catalog-client` (1.16.1 → 1.16.3)](#backstagecatalog-client-1161--1163)
  - [`@backstage/catalog-model` (1.10.0 → 1.10.2)](#backstagecatalog-model-1100--1102)
  - [`@backstage/config` (1.3.8 → 1.3.10)](#backstageconfig-138--1310)
  - [`@backstage/config-loader` (1.11.2 → 1.11.4)](#backstageconfig-loader-1112--1114)
  - [`@backstage/core-app-api` (1.20.4 → 1.20.7-next.0)](#backstagecore-app-api-1204--1207-next0)
  - [`@backstage/errors` (1.3.1 → 1.3.2)](#backstageerrors-131--132)
  - [`@backstage/integration` (2.1.1 → 2.1.3)](#backstageintegration-211--213)
  - [`@backstage/plugin-catalog` (2.0.8 → 2.0.11-next.0)](#backstageplugin-catalog-208--2011-next0)
  - [`@backstage/plugin-search` (1.7.7 → 1.7.10-next.0)](#backstageplugin-search-177--1710-next0)
  - [`@backstage/plugin-search-backend` (2.1.6 → 2.1.9-next.0)](#backstageplugin-search-backend-216--219-next0)
  - [`@backstage/plugin-search-backend-node` (1.4.7 → 1.4.10-next.0)](#backstageplugin-search-backend-node-147--1410-next0)
  - [`@backstage/plugin-techdocs-addons-test-utils` (2.0.8 → 2.0.11-next.0)](#backstageplugin-techdocs-addons-test-utils-208--2011-next0)
  - [`@backstage/plugin-techdocs-module-addons-contrib` (1.1.39 → 1.1.42-next.0)](#backstageplugin-techdocs-module-addons-contrib-1139--1142-next0)
  - [`@backstage/test-utils` (1.7.21 → 1.7.24-next.0)](#backstagetest-utils-1721--1724-next0)
- [Excluded dependency updates](#excluded-dependency-updates)

## Newly added packages

### `@backstage/cli-module-catalog` (new, [0.2.1-next.0](../../changelogs/@backstage/cli-module-catalog.md#021-next0))

#### 0.2.0

##### Minor Changes

- [`3d6721d`](https://github.com/backstage/backstage/commit/3d6721d): Add intent-based CLI modules for catalog, scaffolder, and search.

  New modules provide domain-oriented subcommands that talk directly to the corresponding plugins' REST APIs:

  - `@backstage/cli-module-catalog`: `catalog list`, `catalog get`, `catalog validate`, `catalog register`, `catalog unregister`
  - `@backstage/cli-module-scaffolder`: `template list`, `template execute`, `template dry-run`
  - `@backstage/cli-module-search`: `search`, `docs search`

  The commands take their main input as a positional argument: an entity or template reference, a file path (or `-` for standard input) for `catalog validate` and `template dry-run`, a URL for `catalog register`, and the search terms for `search` and `docs search`. Repeatable `key=value` flags are used for filters, template values, and secrets, and comma-separated lists for `--fields`. Unknown flags are rejected.

  The commands that list results, `catalog list`, `template list`, `search`, and `docs search`, support `--output human` (the default) or `--output json`, along with `--limit` and `--cursor` for paging. Each command prints a single page. Human output shows how many results were shown and, when more are available, prints the `--cursor` value to continue from. All other commands always print JSON. `catalog validate` checks every entity in a multi-document YAML file and prints a JSON array with one result per entity. `catalog validate` and `template dry-run` exit with a non-zero code when the input is invalid, while connection and authentication problems are reported as errors.

  `@backstage/cli-node` now provides shared parsers for repeatable `key=value` inputs and comma-separated lists.

#### 0.2.0-next.0

##### Minor Changes

- [`3d6721d`](https://github.com/backstage/backstage/commit/3d6721d): Add intent-based CLI modules for catalog, scaffolder, and search.

  New modules provide domain-oriented subcommands that talk directly to the corresponding plugins' REST APIs:

  - `@backstage/cli-module-catalog`: `catalog list`, `catalog get`, `catalog validate`, `catalog register`, `catalog unregister`
  - `@backstage/cli-module-scaffolder`: `template list`, `template execute`, `template dry-run`
  - `@backstage/cli-module-search`: `search`, `docs search`

  The commands support human-readable and JSON output, positional entity and template references, repeatable `key=value` filters and inputs, comma-separated fields and search types, and file-based catalog entity and template input.

  `@backstage/cli-node` now provides shared parsers for repeatable `key=value` inputs and comma-separated lists.

### `@backstage/cli-module-package-manager-yarn` (new, [0.1.5-next.0](../../changelogs/@backstage/cli-module-package-manager-yarn.md#015-next0))

#### 0.1.5-next.0

##### Patch Changes

- [`1cffd6f`](https://github.com/backstage/backstage/commit/1cffd6f): Made `@yarnpkg/cli`, `@yarnpkg/core`, and `@yarnpkg/plugin-patch` optional peer dependencies. `@yarnpkg/core@4.9.2` was published with a dependency on a patch file that only exists in the Yarn repository, which made installation fail for all projects depending on this module. To use the `pm verify-patches` command until this is fixed upstream, add these packages as `devDependencies` in your root `package.json`, together with the resolution `"@yarnpkg/core/got": "npm:^11.8.6"`. They will become regular dependencies again once a fixed version of `@yarnpkg/core` is published.

#### 0.1.4

##### Patch Changes

- Bumped version to account for a patch release.

#### 0.1.3

##### Patch Changes

- [`84cfb88`](https://github.com/backstage/backstage/commit/84cfb88): Added a conservative `--fix` mode to `backstage-cli pm verify-patches` that can
  update project-owned Backstage package patches when an automated release
  upgrade leaves them pinned to older versions. The repair requires Yarn 3 or
  later.
- [`673a35d`](https://github.com/backstage/backstage/commit/673a35d): Fixed `backstage-cli pm verify-patches` failing to load unless projects installed the Yarn CLI package separately.

#### 0.1.3-next.2

##### Patch Changes

- [`84cfb88`](https://github.com/backstage/backstage/commit/84cfb88): Added a conservative `--fix` mode to `backstage-cli pm verify-patches` that can
  update project-owned Backstage package patches when an automated release
  upgrade leaves them pinned to older versions. The repair requires Yarn 3 or
  later.

#### 0.1.3-next.0

##### Patch Changes

- [`673a35d`](https://github.com/backstage/backstage/commit/673a35d): Fixed `backstage-cli pm verify-patches` failing to load unless projects installed the Yarn CLI package separately.

#### 0.1.1

##### Patch Changes

- [`de957f6`](https://github.com/backstage/backstage/commit/de957f6): Added `@backstage/cli-module-package-manager-yarn` with `backstage-cli pm
verify-patches` to validate Yarn patch references, local patch files,
  lockfile consistency, and patched Backstage package versions against the
  selected Backstage release. The command is included in
  `@backstage/cli-defaults`.
- [`ce2a9c2`](https://github.com/backstage/backstage/commit/ce2a9c2): The `pm verify-patches` command now reports root-level Yarn resolutions that no longer match any dependency request in the lockfile.
- [`064c2de`](https://github.com/backstage/backstage/commit/064c2de): Updated the Yarn tooling dependencies to versions that avoid known security vulnerabilities.

#### 0.1.1-next.1

##### Patch Changes

- [`064c2de`](https://github.com/backstage/backstage/commit/064c2de): Updated the Yarn tooling dependencies to versions that avoid known security vulnerabilities.

#### 0.1.1-next.0

##### Patch Changes

- [`de957f6`](https://github.com/backstage/backstage/commit/de957f6): Added `@backstage/cli-module-package-manager-yarn` with `backstage-cli pm
verify-patches` to validate Yarn patch references, local patch files,
  lockfile consistency, and patched Backstage package versions against the
  selected Backstage release. The command is included in
  `@backstage/cli-defaults`.

### `@backstage/cli-module-scaffolder` (new, [0.2.1-next.0](../../changelogs/@backstage/cli-module-scaffolder.md#021-next0))

#### 0.2.0

##### Minor Changes

- [`3d6721d`](https://github.com/backstage/backstage/commit/3d6721d): Add intent-based CLI modules for catalog, scaffolder, and search.

  New modules provide domain-oriented subcommands that talk directly to the corresponding plugins' REST APIs:

  - `@backstage/cli-module-catalog`: `catalog list`, `catalog get`, `catalog validate`, `catalog register`, `catalog unregister`
  - `@backstage/cli-module-scaffolder`: `template list`, `template execute`, `template dry-run`
  - `@backstage/cli-module-search`: `search`, `docs search`

  The commands take their main input as a positional argument: an entity or template reference, a file path (or `-` for standard input) for `catalog validate` and `template dry-run`, a URL for `catalog register`, and the search terms for `search` and `docs search`. Repeatable `key=value` flags are used for filters, template values, and secrets, and comma-separated lists for `--fields`. Unknown flags are rejected.

  The commands that list results, `catalog list`, `template list`, `search`, and `docs search`, support `--output human` (the default) or `--output json`, along with `--limit` and `--cursor` for paging. Each command prints a single page. Human output shows how many results were shown and, when more are available, prints the `--cursor` value to continue from. All other commands always print JSON. `catalog validate` checks every entity in a multi-document YAML file and prints a JSON array with one result per entity. `catalog validate` and `template dry-run` exit with a non-zero code when the input is invalid, while connection and authentication problems are reported as errors.

  `@backstage/cli-node` now provides shared parsers for repeatable `key=value` inputs and comma-separated lists.

#### 0.2.0-next.0

##### Minor Changes

- [`3d6721d`](https://github.com/backstage/backstage/commit/3d6721d): Add intent-based CLI modules for catalog, scaffolder, and search.

  New modules provide domain-oriented subcommands that talk directly to the corresponding plugins' REST APIs:

  - `@backstage/cli-module-catalog`: `catalog list`, `catalog get`, `catalog validate`, `catalog register`, `catalog unregister`
  - `@backstage/cli-module-scaffolder`: `template list`, `template execute`, `template dry-run`
  - `@backstage/cli-module-search`: `search`, `docs search`

  The commands support human-readable and JSON output, positional entity and template references, repeatable `key=value` filters and inputs, comma-separated fields and search types, and file-based catalog entity and template input.

  `@backstage/cli-node` now provides shared parsers for repeatable `key=value` inputs and comma-separated lists.

### `@backstage/cli-module-search` (new, [0.2.1-next.0](../../changelogs/@backstage/cli-module-search.md#021-next0))

#### 0.2.0

##### Minor Changes

- [`3d6721d`](https://github.com/backstage/backstage/commit/3d6721d): Add intent-based CLI modules for catalog, scaffolder, and search.

  New modules provide domain-oriented subcommands that talk directly to the corresponding plugins' REST APIs:

  - `@backstage/cli-module-catalog`: `catalog list`, `catalog get`, `catalog validate`, `catalog register`, `catalog unregister`
  - `@backstage/cli-module-scaffolder`: `template list`, `template execute`, `template dry-run`
  - `@backstage/cli-module-search`: `search`, `docs search`

  The commands take their main input as a positional argument: an entity or template reference, a file path (or `-` for standard input) for `catalog validate` and `template dry-run`, a URL for `catalog register`, and the search terms for `search` and `docs search`. Repeatable `key=value` flags are used for filters, template values, and secrets, and comma-separated lists for `--fields`. Unknown flags are rejected.

  The commands that list results, `catalog list`, `template list`, `search`, and `docs search`, support `--output human` (the default) or `--output json`, along with `--limit` and `--cursor` for paging. Each command prints a single page. Human output shows how many results were shown and, when more are available, prints the `--cursor` value to continue from. All other commands always print JSON. `catalog validate` checks every entity in a multi-document YAML file and prints a JSON array with one result per entity. `catalog validate` and `template dry-run` exit with a non-zero code when the input is invalid, while connection and authentication problems are reported as errors.

  `@backstage/cli-node` now provides shared parsers for repeatable `key=value` inputs and comma-separated lists.

#### 0.2.0-next.0

##### Minor Changes

- [`3d6721d`](https://github.com/backstage/backstage/commit/3d6721d): Add intent-based CLI modules for catalog, scaffolder, and search.

  New modules provide domain-oriented subcommands that talk directly to the corresponding plugins' REST APIs:

  - `@backstage/cli-module-catalog`: `catalog list`, `catalog get`, `catalog validate`, `catalog register`, `catalog unregister`
  - `@backstage/cli-module-scaffolder`: `template list`, `template execute`, `template dry-run`
  - `@backstage/cli-module-search`: `search`, `docs search`

  The commands support human-readable and JSON output, positional entity and template references, repeatable `key=value` filters and inputs, comma-separated fields and search types, and file-based catalog entity and template input.

  `@backstage/cli-node` now provides shared parsers for repeatable `key=value` inputs and comma-separated lists.

### `@backstage/plugin-scaffolder-backend-module-workspace-database` (new, [0.1.2-next.0](../../changelogs/@backstage/plugin-scaffolder-backend-module-workspace-database.md#012-next0))

#### 0.1.0

##### Minor Changes

- [`e95b649`](https://github.com/backstage/backstage/commit/e95b649): Added task recovery feature with new `scaffolder.taskRecovery` config section. When enabled, tasks that crash or timeout are automatically recovered and resume from the last completed step, task secrets are retained until the task reaches a terminal state so recovery can continue, and completed step outputs are persisted. Enabling recovery applies to all scaffolder tasks, so actions used by those tasks should be idempotent or use checkpoints. When recovery is disabled (the default), the previous behavior is unchanged: secrets are cleared as soon as a task is claimed and retries re-run every step. The new config consolidates previous experimental flags (`EXPERIMENTAL_recoverTasks`, `EXPERIMENTAL_workspaceSerialization`, `EXPERIMENTAL_recoverTasksTimeout`) which remain supported as fallbacks. The legacy workspace provider setting continues to select a provider only when `EXPERIMENTAL_workspaceSerialization` is `true`.

  Workspace serialization for task recovery now requires installing a separate workspace provider module, including when you use the legacy configuration. For development, use `@backstage/plugin-scaffolder-backend-module-workspace-database` (50 MB limit, not recommended for production). On first startup, that module migrates existing database workspace snapshots from the legacy task storage. For production, use `@backstage/plugin-scaffolder-backend-module-gcp` or a similar external storage provider. The scaffolder rejects a configured provider that has not been installed and registered.

  Enabling crash recovery does not keep completed task event streams open; normal task completion remains terminal for event-stream clients.

#### 0.1.0-next.0

##### Minor Changes

- [`e95b649`](https://github.com/backstage/backstage/commit/e95b649): Added task recovery feature with new `scaffolder.taskRecovery` config section. When enabled, tasks that crash or timeout are automatically recovered and resume from the last completed step, task secrets are retained until the task reaches a terminal state so recovery can continue, and completed step outputs are persisted. Enabling recovery applies to all scaffolder tasks, so actions used by those tasks should be idempotent or use checkpoints. When recovery is disabled (the default), the previous behavior is unchanged: secrets are cleared as soon as a task is claimed and retries re-run every step. The new config consolidates previous experimental flags (`EXPERIMENTAL_recoverTasks`, `EXPERIMENTAL_workspaceSerialization`, `EXPERIMENTAL_recoverTasksTimeout`) which remain supported as fallbacks. The legacy workspace provider setting continues to select a provider only when `EXPERIMENTAL_workspaceSerialization` is `true`.

  Workspace serialization for task recovery now requires installing a separate workspace provider module, including when you use the legacy configuration. For development, use `@backstage/plugin-scaffolder-backend-module-workspace-database` (50 MB limit, not recommended for production). On first startup, that module migrates existing database workspace snapshots from the legacy task storage. For production, use `@backstage/plugin-scaffolder-backend-module-gcp` or a similar external storage provider. The scaffolder rejects a configured provider that has not been installed and registered.

  Enabling crash recovery does not keep completed task event streams open; normal task completion remains terminal for event-stream clients.

### `@backstage/plugin-techdocs-backend-module-zensical` (new, [0.1.0-next.0](../../changelogs/@backstage/plugin-techdocs-backend-module-zensical.md#010-next0))

#### 0.1.0-next.0

##### Minor Changes

- [`a4604d2`](https://github.com/backstage/backstage/commit/a4604d2): New module that adds [Zensical](https://zensical.org) as an experimental TechDocs documentation engine. Opt entities in with the `backstage.io/techdocs-engine: zensical` annotation, or set `techdocs.generator.defaultEngine: zensical`. See [Zensical Engine](https://backstage.io/docs/features/techdocs/engines-zensical) for setup and configuration.

## Breaking changes

### `@backstage/backend-plugin-api` (1.10.0 → [1.11.1-next.0](../../changelogs/@backstage/backend-plugin-api.md#1111-next0))

#### 1.11.0

##### Minor Changes

- [`e956084`](https://github.com/backstage/backstage/commit/e956084): **BREAKING PRODUCERS**: Added an instance ID to the root instance metadata service. Custom implementations and mocks must now provide a globally unique ID that remains stable for the lifetime of the running backend instance.
- [`f6054ac`](https://github.com/backstage/backstage/commit/f6054ac): Added experimental `declareConnection` and `connectionsServiceRef` exports to `@backstage/backend-plugin-api/alpha`. Plugins and modules can declare connection dependencies and request the connections service without importing private packages.

#### 1.11.0-next.2

##### Minor Changes

- [`f6054ac`](https://github.com/backstage/backstage/commit/f6054ac): Added experimental `declareConnection` and `connectionsServiceRef` exports to `@backstage/backend-plugin-api/alpha`. Plugins and modules can declare connection dependencies and request the connections service without importing private packages.

#### 1.11.0-next.1

##### Minor Changes

- [`e956084`](https://github.com/backstage/backstage/commit/e956084): **BREAKING PRODUCERS**: Added an instance ID to the root instance metadata service. Custom implementations and mocks must now provide a globally unique ID that remains stable for the lifetime of the running backend instance.

### `@backstage/connections` (0.3.0 → [0.4.1](../../changelogs/@backstage/connections.md#041))

#### 0.4.1

##### Patch Changes

- [`e3b418c`](https://github.com/backstage/backstage/commit/e3b418c): Fixed the `Connection` type so that `auth` is a union of method variants instead of an array when no specific auth method is provided.

#### 0.4.0

##### Minor Changes

- [`d86c47f`](https://github.com/backstage/backstage/commit/d86c47f): **BREAKING**: Cleaned up the public API surface with the following changes:

  - Renamed `ConnectionAuthValue` to `ConnectionAuth`
  - Renamed `LookupStrategy` to `ConnectionLookupStrategy`
  - Removed `ConnectionAuthMatch` (inlined as `{ plugins: string[] }`)
  - Removed `ConnectionAuthMethodKey` (inlined where used)
  - Broadened the `buildConnectionsFromConfig` logger option to accept any logger with `error`, `warn`, `info`, and `debug` methods
  - Moved `buildConnectionsFromConfig`, `ConfiguredConnection`, and `ConfiguredConnectionAuth` to a new `@backstage/connections/config` sub-path export
  - Removed `matchAuth` and `validate` from the public `ConnectionType` shape
  - Renamed `ConnectionType` to `ConnectionTypeDefinition` (the definition object describing a connection type's schemas and behavior)
  - Renamed `ConnectionTypeKey` to `ConnectionType` (the string union of registered connection type names)
  - Renamed `isConnectionTypeKey` to `isConnectionType`
  - Repurposed `ConnectionAuth` as a consumer-facing lookup type: `ConnectionAuth<'aws'>` resolves to the union of auth entry shapes, `ConnectionAuth<'github', 'token'>` narrows to a single method

- [`06cd10c`](https://github.com/backstage/backstage/commit/06cd10c): Removed the nonexistent `query` and `auth` properties from connection type descriptors, along with the unused `AuthValue` type. Query and returned authentication types remain inferred through `ConnectionsService.find`.

##### Patch Changes

- [`736d84e`](https://github.com/backstage/backstage/commit/736d84e): Use locale-insensitive Unicode casing for consistent string handling across environments.
- [`9cf2287`](https://github.com/backstage/backstage/commit/9cf2287): Added support for calling `find` without `authMethods`, which returns connection info (type, title, and config fields) without any auth data. This is useful for consumers that only need connection metadata like API base URLs and don't handle authentication themselves.

### `@backstage/filter-predicates` (0.1.4 → [0.2.0](../../changelogs/@backstage/filter-predicates.md#020))

#### 0.2.0

##### Minor Changes

- [`11f608b`](https://github.com/backstage/backstage/commit/11f608b): **BREAKING**: The `FilterPredicate` type, the zod schemas and `parseFilterPredicate` now only accept objects at the root of a predicate. Primitive values such as `"component"` or `true` were previously accepted at the root, but no API that accepts filter predicates could match them in a meaningful way. Primitive values are still allowed as values to match against properties, and as the operand of `$contains` to match arrays of primitive values, for example `{ "metadata.tags": { "$contains": "java" } }`.

  A new `AnyFilterPredicate` type describes predicates that may also be primitive values at the root, which is equivalent to the previous `FilterPredicate` type. It is used for the operand of `$contains`, and is accepted by `evaluateFilterPredicate`.

#### 0.1.5

##### Patch Changes

- [`736d84e`](https://github.com/backstage/backstage/commit/736d84e): Use locale-insensitive Unicode casing for consistent string handling across environments.
- [`603e704`](https://github.com/backstage/backstage/commit/603e704): The JSON Schema exported for filter predicates can now be compiled by validators built on RE2 (for example Go's `regexp`, used by Amazon Bedrock AgentCore Gateway), which previously rejected the predicate key pattern and failed every call to tools such as `query-catalog-entities`. Accepted keys are unchanged, except that a key whose first character is U+2028 or U+2029 is no longer rejected.
- [`6dcb08a`](https://github.com/backstage/backstage/commit/6dcb08a): Reduced the frontend bundle size by letting bundlers tree-shake zod, which previously pulled every zod locale into the bundle. Takes effect on zod 4.5.0 and newer.

### `@backstage/frontend-test-utils` (0.6.3 → [0.7.0-next.0](../../changelogs/@backstage/frontend-test-utils.md#070-next0))

#### 0.7.0-next.0

##### Minor Changes

- [`8ca78a2`](https://github.com/backstage/backstage/commit/8ca78a2): **BREAKING** Updated `renderInTestApp` and `renderTestApp` to provide default API implementations that are more suitable for testing. This may break existing tests that rely on the previous defaults:

  - **Toasts** are collected in memory instead of being displayed. Tests that assert on visible notifications need to provide an API implementation that forwards toasts to the UI, or assert on an explicitly supplied toast fake instead.
  - **Storage** is isolated in memory for each test app instead of using browser `localStorage`. Tests that seed or inspect `localStorage`, or rely on storage persisting between test apps, need to supply an explicit storage implementation.
  - **Errors** are collected without forwarding them to alerts or installing global error handlers. Error subscriptions no longer receive events from the default implementation. Tests that rely on these behaviors need an explicit error API implementation; tests can also supply a collecting error fake to assert on reported errors.
  - **Alerts** are collected and delivered to current subscribers, but earlier alerts are no longer replayed to new subscribers. Tests that rely on replay need an explicit alert API implementation.
  - **OAuth requests** use an in-memory coordinator with the same request coordination behavior as before.

  Explicit API overrides continue to take precedence over the defaults.

  Added `mockApis` helpers for all APIs in `coreApis`, including app state, dialogs, icons, OAuth requests, plugin wrappers and header actions, route resolution, swappable components, and toast notifications. Each `.mock()` helper provides typed Jest stubs without default behavior that can be registered directly with frontend test utilities.

  Added functional in-memory fakes for language, lifecycle, themes, icons, OAuth requests, plugin header actions, and toast notifications. Except for lifecycle, these can be supplied explicitly through the test app's `apis` option to configure behavior and inspect state. Use `TestApiProvider` for the lifecycle fake, since test apps manage their own lifecycle.

  Fixed storage fake isolation for nested buckets with the same name under different parents.

#### 0.6.5

##### Patch Changes

- [`8747376`](https://github.com/backstage/backstage/commit/8747376): Declared the dependencies of internally bundled code so that the package works with strict `node_modules` layouts.

#### 0.6.4

##### Patch Changes

- [`279fdf6`](https://github.com/backstage/backstage/commit/279fdf6): Declared the DOM Testing Library dependency required by React Testing Library.

#### 0.6.4-next.1

##### Patch Changes

- [`279fdf6`](https://github.com/backstage/backstage/commit/279fdf6): Declared the DOM Testing Library dependency required by React Testing Library.

### `@backstage/plugin-auth-backend-module-atlassian-provider` (0.4.18 → [0.5.1-next.0](../../changelogs/@backstage/plugin-auth-backend-module-atlassian-provider.md#051-next0))

#### 0.5.0

##### Minor Changes

- [`d7cd08b`](https://github.com/backstage/backstage/commit/d7cd08b): **BREAKING**: Removed the `usernameMatchingUserEntityName` sign-in resolver, along with the `atlassianSignInResolvers` export that only contained it. Atlassian user profiles do not contain a username, so the resolver could never work in an Atlassian environment anyway. Use the `emailMatchingUserEntityProfileEmail` or `emailLocalPartMatchingUserEntityName` resolvers instead.

### `@backstage/plugin-auth-backend-module-cloudflare-access-provider` (0.4.18 → [0.5.2-next.0](../../changelogs/@backstage/plugin-auth-backend-module-cloudflare-access-provider.md#052-next0))

#### 0.5.2-next.0

##### Patch Changes

- [`918ca98`](https://github.com/backstage/backstage/commit/918ca98): Updated dependency `jose` to `^6.1.0`. Existing ES256 token issuance and verification are unchanged. ML-DSA algorithms can be used when the runtime supports them.

#### 0.5.0

##### Minor Changes

- [`ed9034c`](https://github.com/backstage/backstage/commit/ed9034c): **BREAKING**: The Cloudflare Access provider now requires the application audience in its configuration. Before upgrading, set `auth.providers.cfaccess.audience` to the Audience (AUD) tag shown for your Backstage application in Cloudflare Zero Trust.

  ```yaml
  auth:
    providers:
      cfaccess:
        teamName: example
        audience: ${AUTH_CFACCESS_AUDIENCE}
  ```

### `@backstage/plugin-catalog-backend` (3.9.1 → [4.0.3-next.0](../../changelogs/@backstage/plugin-catalog-backend.md#403-next0))

#### 4.0.3-next.0

##### Patch Changes

- [`7d765b6`](https://github.com/backstage/backstage/commit/7d765b6): Improved repository validation for catalog entity placeholders. Placeholder-driven reads, including `$openapi` and `$asyncapi` document references, are now restricted to the entity's own repository on SCM hosts; cross-repository references are rejected.
- [`2a9f08b`](https://github.com/backstage/backstage/commit/2a9f08b): Match URL locations in catalog rules in canonical form.

  URL locations are now matched against catalog rules in a canonical form of the URL, so that rule decisions agree with how the location target is resolved when its content is fetched. URL patterns that relied on percent-encoded characters being matched as written, or on default ports being kept, no longer match and should be updated.

#### 4.0.2

##### Patch Changes

- Bumped version to account for a patch release.

#### 4.0.1

##### Patch Changes

- [`589dcef`](https://github.com/backstage/backstage/commit/589dcef): Fixed an issue where successfully processed entities could remain unavailable if stitch scheduling was interrupted.
- [`a08e746`](https://github.com/backstage/backstage/commit/a08e746): Improved large entity provider mutations by yielding to the event loop while preparing database changes.
- [`aa6e7c6`](https://github.com/backstage/backstage/commit/aa6e7c6): Reduce repeated work for entities that fail stitching by gradually increasing retry delays with jitter. Failed entities remain eligible for recovery, and new stitching requests reset their failure count.
- [`d7cc6e5`](https://github.com/backstage/backstage/commit/d7cc6e5): Reject non-positive stitching polling intervals and lease durations at startup to prevent continuous polling and immediate lease expiry. Configuration errors identify the setting that needs correction.
- [`727d53f`](https://github.com/backstage/backstage/commit/727d53f): Improve responsiveness to other requests while reading large sets of entities with field selection, without reducing page sizes.

  Like full-entity responses, projected list responses may now be streamed without a `Content-Length` or automatically generated `ETag` header.

- [`11f608b`](https://github.com/backstage/backstage/commit/11f608b): Entity and location queries with a primitive value at the root of the filter predicate are now rejected with an "Invalid query" error, rather than "Query must be an object".
- [`e783f4b`](https://github.com/backstage/backstage/commit/e783f4b): Fixed catalog processing error messages to report stable processor names in minified builds.
- [`7c376ff`](https://github.com/backstage/backstage/commit/7c376ff): Improved the performance and planner stability of orphan entity cleanup on large PostgreSQL catalogs. Orphan deletion and updates to related entities are now atomic, so a failed cleanup does not leave related entities waiting indefinitely for updated relations. Cleanup also preserves entities when a new reference is committed while it waits to delete them.
- [`a69d971`](https://github.com/backstage/backstage/commit/a69d971): Improved the reliability of deferred stitching. Pending stitching work is no longer lost when entities are deleted and re-added, and updated instances prevent timed-out stitching attempts from overwriting or removing work taken over by another updated instance. During rolling upgrades from older versions, instances may still perform redundant stitching. On MySQL, protection against overlapping writes remains best-effort.
- [`476f042`](https://github.com/backstage/backstage/commit/476f042): Fixed entities disappearing from filtered and sorted catalog queries after a database error during stitching. The final entity and its search index rows are now written together, so a failure part way through is rolled back and retried in full. Previously the entity could be left with a search index that no longer matched it, and because the entity itself looked up to date, every later stitch attempt skipped it. Such an entity stayed readable by direct lookup while missing from list queries that filter or sort, until it was next edited.

  PostgreSQL and MySQL deadlocks trigger prompt, bounded retries of the entire write transaction, skipping the write if newer stitching work has superseded it. If retries are exhausted, queued work remains available for recovery after the stitching timeout.

#### 4.0.1-next.3

##### Patch Changes

- [`aa6e7c6`](https://github.com/backstage/backstage/commit/aa6e7c6): Reduce repeated work for entities that fail stitching by gradually increasing retry delays with jitter. Failed entities remain eligible for recovery, and new stitching requests reset their failure count.
- [`d7cc6e5`](https://github.com/backstage/backstage/commit/d7cc6e5): Reject non-positive stitching polling intervals and lease durations at startup to prevent continuous polling and immediate lease expiry. Configuration errors identify the setting that needs correction.
- [`7c376ff`](https://github.com/backstage/backstage/commit/7c376ff): Improved the performance and planner stability of orphan entity cleanup on large PostgreSQL catalogs. Orphan deletion and updates to related entities are now atomic, so a failed cleanup does not leave related entities waiting indefinitely for updated relations. Cleanup also preserves entities when a new reference is committed while it waits to delete them.

#### 4.0.1-next.2

##### Patch Changes

- [`589dcef`](https://github.com/backstage/backstage/commit/589dcef): Fixed an issue where successfully processed entities could remain unavailable if stitch scheduling was interrupted.
- [`a69d971`](https://github.com/backstage/backstage/commit/a69d971): Improved the reliability of deferred stitching. Pending stitching work is no longer lost when entities are deleted and re-added, and updated instances prevent timed-out stitching attempts from overwriting or removing work taken over by another updated instance. During rolling upgrades from older versions, instances may still perform redundant stitching. On MySQL, protection against overlapping writes remains best-effort.
- [`476f042`](https://github.com/backstage/backstage/commit/476f042): Fixed entities disappearing from filtered and sorted catalog queries after a database error during stitching. The final entity and its search index rows are now written together, so a failure part way through is rolled back and retried in full. Previously the entity could be left with a search index that no longer matched it, and because the entity itself looked up to date, every later stitch attempt skipped it. Such an entity stayed readable by direct lookup while missing from list queries that filter or sort, until it was next edited.

  PostgreSQL and MySQL deadlocks trigger prompt, bounded retries of the entire write transaction, skipping the write if newer stitching work has superseded it. If retries are exhausted, queued work remains available for recovery after the stitching timeout.

#### 4.0.1-next.0

##### Patch Changes

- [`a08e746`](https://github.com/backstage/backstage/commit/a08e746): Improved large entity provider mutations by yielding to the event loop while preparing database changes.
- [`727d53f`](https://github.com/backstage/backstage/commit/727d53f): Improve responsiveness to other requests while reading large sets of entities with field selection, without reducing page sizes.

  Like full-entity responses, projected list responses may now be streamed without a `Content-Length` or automatically generated `ETag` header.

- [`e783f4b`](https://github.com/backstage/backstage/commit/e783f4b): Fixed catalog processing error messages to report stable processor names in minified builds.

#### 4.0.0

##### Major Changes

- [`b0d8a53`](https://github.com/backstage/backstage/commit/b0d8a53): **BREAKING**: Removed the deprecated `CodeOwnersProcessor` and `AnnotateScmSlugEntityProcessor` exports. To retain their behavior, install and register the corresponding community backend module:

  - `CodeOwnersProcessor`: [`@backstage-community/plugin-catalog-backend-module-codeowners`](https://github.com/backstage/community-plugins/tree/main/workspaces/catalog/plugins/catalog-backend-module-codeowners)
  - `AnnotateScmSlugEntityProcessor`: [`@backstage-community/plugin-catalog-backend-module-annotate-scm-slug`](https://github.com/backstage/community-plugins/tree/main/workspaces/catalog/plugins/catalog-backend-module-annotate-scm-slug)

  Add the module to your backend with `backend.add(import('<module-package>'))` and remove the custom registration of the old processor. For explicit processor configuration, follow the replacement module's documentation.

- [`b0d8a53`](https://github.com/backstage/backstage/commit/b0d8a53): **BREAKING**: Removed the deprecated `catalog.stitchingStrategy.mode` configuration setting and its startup warnings. Remove this key from your configuration, whether it is set to `immediate` or `deferred`. Stitching continues to run asynchronously via the worker queue. The `catalog.stitchingStrategy.pollingInterval` and `catalog.stitchingStrategy.stitchTimeout` settings remain supported and should be kept if you use them.
- [`d2cf99f`](https://github.com/backstage/backstage/commit/d2cf99f): **BREAKING**: Removed the deprecated `catalog.enableRelationsCompatibility` config option and its associated compatibility layer. Entity relations are now always returned in the standard format with only `targetRef`. If you were relying on the `target` field in relations, update your code to use `targetRef` instead.

##### Patch Changes

- [`736d84e`](https://github.com/backstage/backstage/commit/736d84e): Use locale-insensitive Unicode casing for consistent string handling across environments.
- [`f5119cc`](https://github.com/backstage/backstage/commit/f5119cc): Improved PostgreSQL catalog query planning by correcting entity cardinality statistics for the search table.
- [`72c16f5`](https://github.com/backstage/backstage/commit/72c16f5): Use stable PostgreSQL array parameters for `$in` filter predicates.
- [`78656f8`](https://github.com/backstage/backstage/commit/78656f8): Fixed catalog model relations to inherit the source entity namespace when no default namespace is configured, as documented. Explicit namespaces in entity references and explicitly configured default namespaces continue to take precedence.
- [`7761a50`](https://github.com/backstage/backstage/commit/7761a50): Improved path validation for catalog entity placeholders.
- [`49b41f6`](https://github.com/backstage/backstage/commit/49b41f6): Fixed a bug where catalog entities could fail to process when catalog model sources are enabled and the catalog mixes `backstage.io/v1alpha1` and `backstage.io/v1beta1` for the same kind.
- [`4b922b3`](https://github.com/backstage/backstage/commit/4b922b3): The `catalog:query-catalog-entities` action now accepts `limit` and `offset` when they are passed as strings, coercing them to numbers before validation. Previously the action failed with a validation error when a client sent these pagination arguments as strings, which is common for MCP/LLM clients.
- [`fda0ef1`](https://github.com/backstage/backstage/commit/fda0ef1): Correct catalog property permission matching.
- [`ff327e0`](https://github.com/backstage/backstage/commit/ff327e0): Apply catalog location analysis permissions consistently when using a custom location analyzer.
- [`05e2005`](https://github.com/backstage/backstage/commit/05e2005): Fixed PostgreSQL catalog migrations sometimes failing during search index deduplication when using a database connection pool.
- [`7629e5e`](https://github.com/backstage/backstage/commit/7629e5e): Use stable PostgreSQL array parameters for batched refresh state lookups and updates.
- [`c26a19b`](https://github.com/backstage/backstage/commit/c26a19b): Improved catalog database performance stability for large PostgreSQL installations with frequent entity updates.
- [`e363ae2`](https://github.com/backstage/backstage/commit/e363ae2): Allowed location type restrictions are now applied consistently during catalog processing.

#### 4.0.0-next.1

##### Major Changes

- [`d2cf99f`](https://github.com/backstage/backstage/commit/d2cf99f): **BREAKING**: Removed the deprecated `catalog.enableRelationsCompatibility` config option and its associated compatibility layer. Entity relations are now always returned in the standard format with only `targetRef`. If you were relying on the `target` field in relations, update your code to use `targetRef` instead.

##### Patch Changes

- [`f5119cc`](https://github.com/backstage/backstage/commit/f5119cc): Improved PostgreSQL catalog query planning by correcting entity cardinality statistics for the search table.
- [`72c16f5`](https://github.com/backstage/backstage/commit/72c16f5): Use stable PostgreSQL array parameters for `$in` filter predicates.
- [`7629e5e`](https://github.com/backstage/backstage/commit/7629e5e): Use stable PostgreSQL array parameters for batched refresh state lookups and updates.

#### 3.9.2-next.0

##### Patch Changes

- [`7761a50`](https://github.com/backstage/backstage/commit/7761a50): Improved path validation for catalog entity placeholders.
- [`fda0ef1`](https://github.com/backstage/backstage/commit/fda0ef1): Correct catalog property permission matching.
- [`e363ae2`](https://github.com/backstage/backstage/commit/e363ae2): Allowed location type restrictions are now applied consistently during catalog processing.

### `@backstage/plugin-catalog-backend-module-incremental-ingestion` (0.7.15 → [0.9.1-next.0](../../changelogs/@backstage/plugin-catalog-backend-module-incremental-ingestion.md#091-next0))

#### 0.9.0

##### Minor Changes

- [`e003123`](https://github.com/backstage/backstage/commit/e003123): Added a `source_key` column and a `UNIQUE(source_key, entity_ref)` constraint to the `ingestion_mark_entities` table, enabling a single native upsert instead of a select-then-update-or-insert sequence per ingestion mark.
  This significantly reduces the number of database round trips during ingestion.

  As part of this change, the table's `ref` column is renamed to `entity_ref` to standardize its naming with the rest of the table's columns.
  This rename means the migration cannot be applied as part of a rolling, zero-downtime upgrade, which is fine since incremental ingestion providers are designed to run sequentially on a single Backstage backend instance.

#### 0.9.0-next.0

##### Minor Changes

- [`e003123`](https://github.com/backstage/backstage/commit/e003123): Added a `source_key` column and a `UNIQUE(source_key, entity_ref)` constraint to the `ingestion_mark_entities` table, enabling a single native upsert instead of a select-then-update-or-insert sequence per ingestion mark.
  This significantly reduces the number of database round trips during ingestion.

  As part of this change, the table's `ref` column is renamed to `entity_ref` to standardize its naming with the rest of the table's columns.
  This rename means the migration cannot be applied as part of a rolling, zero-downtime upgrade, which is fine since incremental ingestion providers are designed to run sequentially on a single Backstage backend instance.

#### 0.8.0

##### Minor Changes

- [`305e2f7`](https://github.com/backstage/backstage/commit/305e2f7): **BREAKING**: The incremental ingestion administrative routes now enforce separate read and manage permissions. Installations with custom permission policies must add decisions for the new permissions.

#### 0.8.0-next.1

##### Minor Changes

- [`305e2f7`](https://github.com/backstage/backstage/commit/305e2f7): **BREAKING**: The incremental ingestion administrative routes now enforce separate read and manage permissions. Installations with custom permission policies must add decisions for the new permissions.

### `@backstage/plugin-kubernetes-react` (0.5.23 → [0.6.2-next.0](../../changelogs/@backstage/plugin-kubernetes-react.md#062-next0))

#### 0.6.1

##### Patch Changes

- [`76ac6ed`](https://github.com/backstage/backstage/commit/76ac6ed): Updated dependency `js-yaml` to `^5.0.0`.

#### 0.6.1-next.1

##### Patch Changes

- [`76ac6ed`](https://github.com/backstage/backstage/commit/76ac6ed): Updated dependency `js-yaml` to `^5.0.0`.

#### 0.6.0

##### Minor Changes

- [`cfba1bc`](https://github.com/backstage/backstage/commit/cfba1bc): **BREAKING PRODUCERS:** The `FixDialog`, `ContainerCard`, and `PodLogs` components no longer accept an implicit `children` prop. This aligns them with ADR006. If you were passing children to these components, remove them as they were never rendered.

##### Patch Changes

- [`736d84e`](https://github.com/backstage/backstage/commit/736d84e): Use locale-insensitive Unicode casing for consistent string handling across environments.
- [`c0ebaa7`](https://github.com/backstage/backstage/commit/c0ebaa7): chore(deps): bump `js-yaml` from 4.3.1 to 4.3.2
- [`83f34f2`](https://github.com/backstage/backstage/commit/83f34f2): The pod exec terminal now loads `@xterm/xterm` and its stylesheet when a terminal is opened, instead of including them in the initial bundle.

#### 0.6.0-next.2

##### Minor Changes

- [`cfba1bc`](https://github.com/backstage/backstage/commit/cfba1bc): **BREAKING PRODUCERS:** The `FixDialog`, `ContainerCard`, and `PodLogs` components no longer accept an implicit `children` prop. This aligns them with ADR006. If you were passing children to these components, remove them as they were never rendered.

#### 0.5.24-next.1

##### Patch Changes

- [`83f34f2`](https://github.com/backstage/backstage/commit/83f34f2): The pod exec terminal now loads `@xterm/xterm` and its stylesheet when a terminal is opened, instead of including them in the initial bundle.

### `@backstage/plugin-scaffolder-backend-module-gcp` (0.2.24 → [0.3.0-next.0](../../changelogs/@backstage/plugin-scaffolder-backend-module-gcp.md#030-next0))

#### 0.3.0-next.0

##### Minor Changes

- [`44d5ba2`](https://github.com/backstage/backstage/commit/44d5ba2): **BREAKING**: The backend's Google Cloud credentials now require the `storage.objects.list` permission on the configured task recovery bucket, in addition to the existing object permissions. Grant this permission before upgrading.

  Fixed task recovery workspace saves failing with Google Cloud Storage rate limit errors when template steps finish in quick succession. Each snapshot is saved to a separate object, and recovery continues to support snapshots from older versions.

#### 0.2.25

##### Patch Changes

- [`e95b649`](https://github.com/backstage/backstage/commit/e95b649): Added new config path `scaffolder.taskRecovery.gcsBucket.name` for GCS workspace provider. The previous `EXPERIMENTAL_workspaceSerializationGcpBucketName` config is still supported as a fallback. Workspace upload failures are now propagated so that a task does not record a completed step without its corresponding workspace.

#### 0.2.25-next.0

##### Patch Changes

- [`e95b649`](https://github.com/backstage/backstage/commit/e95b649): Added new config path `scaffolder.taskRecovery.gcsBucket.name` for GCS workspace provider. The previous `EXPERIMENTAL_workspaceSerializationGcpBucketName` config is still supported as a fallback. Workspace upload failures are now propagated so that a task does not record a completed step without its corresponding workspace.

### `@backstage/plugin-scaffolder-backend-module-github` (0.9.13 → [0.10.2-next.0](../../changelogs/@backstage/plugin-scaffolder-backend-module-github.md#0102-next0))

#### 0.10.0

##### Minor Changes

- [`aced3e4`](https://github.com/backstage/backstage/commit/aced3e4): **BREAKING**: Removed unused inputs from the `github:repo:create` action schema. The following inputs were previously accepted but silently ignored, and have now been removed: `blockCreations`, `branch`, `bypassPullRequestAllowances`, `defaultBranch`, `dismissStaleReviews`, `gitAuthorEmail`, `gitAuthorName`, `gitCommitMessage`, `protectDefaultBranch`, `protectEnforceAdmins`, `requireBranchesToBeUpToDate`, `requireCodeOwnerReviews`, `requiredApprovingReviewCount`, `requiredCommitSigning`, `requiredConversationResolution`, `requiredLinearHistory`, `requiredStatusCheckContexts`, `requireLastPushApproval`, `restrictions`, and `sourcePath`. If your templates pass any of these to `github:repo:create`, remove them. Most of these inputs are supported by the `github:repo:push` action for branch protection, git authoring, and content publishing.

##### Patch Changes

- [`bbba6b5`](https://github.com/backstage/backstage/commit/bbba6b5): Added support for requiring user-provided credentials for GitHub mutation actions when `scaffolder.requireScmUserCredentials` is enabled.
- [`736d84e`](https://github.com/backstage/backstage/commit/736d84e): Use locale-insensitive Unicode casing for consistent string handling across environments.

#### 0.9.14-next.1

##### Patch Changes

- [`bbba6b5`](https://github.com/backstage/backstage/commit/bbba6b5): Added support for requiring user-provided credentials for GitHub mutation actions when `scaffolder.requireScmUserCredentials` is enabled.

### `@backstage/plugin-scaffolder-backend-module-sentry` (0.3.7 → [0.4.2-next.0](../../changelogs/@backstage/plugin-scaffolder-backend-module-sentry.md#042-next0))

#### 0.4.0

##### Minor Changes

- [`52b5c79`](https://github.com/backstage/backstage/commit/52b5c79): **BREAKING**: Restrict Sentry API requests to the configured API base URL. Move custom action-level `apiBaseUrl` values to `scaffolder.sentry.apiBaseUrl` before upgrading.

### `@backstage/plugin-search-backend-module-elasticsearch` (1.8.7 → [2.0.2-next.0](../../changelogs/@backstage/plugin-search-backend-module-elasticsearch.md#202-next0))

#### 2.0.2-next.0

##### Patch Changes

- [`8da9c23`](https://github.com/backstage/backstage/commit/8da9c23): Internal changes for TypeScript 7 compatibility. There are no changes to behavior or the public API.

#### 2.0.1

##### Patch Changes

- [`2153e90`](https://github.com/backstage/backstage/commit/2153e90): Fixed search queries intermittently failing with a 500 error when a collator finished indexing. The index that the search alias pointed to before the rotation is no longer deleted immediately, so queries already running against it can complete. It is instead removed during the next indexing run for that document type. Note that this means the previous index is now retained between runs, so search storage usage per document type is roughly doubled.

  Also improved error reporting for failed search queries. An index that disappears while a query is running is now reported as a missing index, and other query failures now include the underlying cause in the logs instead of `undefined`.

#### 2.0.0

##### Major Changes

- [`3753c36`](https://github.com/backstage/backstage/commit/3753c36): **BREAKING**: Upgraded the Elasticsearch client to version 8, requiring at least version 8.19 - the only 8.x release line still under support, [following the end of life of Elasticsearch 7.x and earlier 8.x lines](https://endoflife.date/elasticsearch). Elasticsearch 7.x clusters are no longer supported.

  If you use the `elastic` provider or connect to a plain Elasticsearch node, make sure your cluster is running Elasticsearch 8.19 or later before upgrading. The `aws` and `opensearch` providers keep using the OpenSearch client and are unaffected. Existing TLS settings continue to work without any configuration changes.

  The methods of the `ElasticSearchClientWrapper` now return a normalized response that exposes `body`, `statusCode`, `headers` and `warnings` for both providers, instead of the client specific response types. Code that relies on the raw client types or reads the `meta` property of a response needs to be adjusted.

##### Patch Changes

- [`fe6ace6`](https://github.com/backstage/backstage/commit/fe6ace6): Added optional `accountId` config to `search.elasticsearch` for resolving account-specific AWS credentials, enabling support for `webIdentityTokenFile` and `accountDefaults` when using AWS OpenSearch.
- [`b11c9b4`](https://github.com/backstage/backstage/commit/b11c9b4): Fixed a bug where an empty document type list could result in querying all indices instead of returning empty results.

#### 1.8.8-next.0

##### Patch Changes

- [`b11c9b4`](https://github.com/backstage/backstage/commit/b11c9b4): Fixed a bug where an empty document type list could result in querying all indices instead of returning empty results.

### `@backstage/plugin-techdocs-node` (1.15.4 → [2.2.0-next.0](../../changelogs/@backstage/plugin-techdocs-node.md#220-next0))

#### 2.2.0-next.0

##### Minor Changes

- [`a4604d2`](https://github.com/backstage/backstage/commit/a4604d2): Added a new `@backstage/plugin-techdocs-node/alpha` entry point with building blocks for implementing additional documentation engines in separate modules: `createDockerContainerRunner`, `createOrUpdateMetadata`, `storeEtagMetadata`, `runCommand`, `validateInputDirectory`, `patchIndexPreBuild`, and the `mkdocs.yml` helpers `MKDOCS_SCHEMA`, `validateMkdocsYaml` and `sanitizeMkdocsYml`. These are alpha and may change in minor releases.

##### Patch Changes

- [`686d3cb`](https://github.com/backstage/backstage/commit/686d3cb): Fixed TechDocs served from Azure Blob Storage or Google Cloud Storage keeping storage connections open when a browser navigates away before a file is fully loaded. Errors that occur while streaming a file from Azure Blob Storage are now also logged and handled, instead of being left unhandled.
- [`2e98895`](https://github.com/backstage/backstage/commit/2e98895): Fixed TechDocs served from AWS S3 leaking S3 connections when a browser navigates away before a file is fully loaded. Over time the connection pool was exhausted and all TechDocs pages failed to load with `Socket timed out without establishing a connection` errors until the backend was restarted.

#### 2.1.0

##### Minor Changes

- [`4d4f987`](https://github.com/backstage/backstage/commit/4d4f987): Add engine abstraction layer for multi-engine TechDocs support. Introduces `--engine` flag, engine config map, generator registry with `backstage.io/techdocs-engine` annotation support, `engine` field in `techdocs_metadata.json`, `serve:raw` command, and live-reload adapter interface. MkDocs remains the default with no behavior change.

  The built-in generator is now registered under `mkdocs`; the previous `techdocs` key is kept as an alias, so existing `generators.register('techdocs', ...)` calls continue to work. The CLI's `--engine` flag takes precedence over the `backstage.io/techdocs-engine` annotation for all commands, and `serve:mkdocs` and the `--mkdocs-parameter-*` flags now print deprecation warnings.

##### Patch Changes

- [`9fc5387`](https://github.com/backstage/backstage/commit/9fc5387): Improved handling of mapping-style Markdown extension configuration.
- [`0fd5fe5`](https://github.com/backstage/backstage/commit/0fd5fe5): Fixed TechDocs allowing `custom_icons` paths in `mkdocs.yml` that resolve outside the documentation input directory. A `custom_icons` option with such a path is now removed from the configuration with a warning.
- [`8a37336`](https://github.com/backstage/backstage/commit/8a37336): Fixed TechDocs generation rejecting `mkdocs.yml` files that use the emoji indexes and generators or the `pymdownx.superfences` custom fence formats documented by mkdocs-material, pymdown-extensions and mkdocs-mermaid2.
- [`76ac6ed`](https://github.com/backstage/backstage/commit/76ac6ed): Updated dependency `js-yaml` to `^5.0.0`.

#### 2.0.3-next.2

##### Patch Changes

- [`76ac6ed`](https://github.com/backstage/backstage/commit/76ac6ed): Updated dependency `js-yaml` to `^5.0.0`.

#### 2.0.3-next.1

##### Patch Changes

- Bumped version to account for a patch release.

#### 2.0.2-next.1

##### Patch Changes

- [`9fc5387`](https://github.com/backstage/backstage/commit/9fc5387): Improved handling of mapping-style Markdown extension configuration.
- [`0fd5fe5`](https://github.com/backstage/backstage/commit/0fd5fe5): Fixed TechDocs allowing `custom_icons` paths in `mkdocs.yml` that resolve outside the documentation input directory. A `custom_icons` option with such a path is now removed from the configuration with a warning.
- [`8a37336`](https://github.com/backstage/backstage/commit/8a37336): Fixed TechDocs generation rejecting `mkdocs.yml` files that use the emoji indexes and generators or the `pymdownx.superfences` custom fence formats documented by mkdocs-material, pymdown-extensions and mkdocs-mermaid2.

#### 2.0.0

##### Major Changes

- [`62d1a6f`](https://github.com/backstage/backstage/commit/62d1a6f): **BREAKING**: TechDocs generation now removes MkDocs plugins outside the built-in allowlist and logs a warning before continuing the build. To retain additional plugins, review and add them to `techdocs.generator.mkdocs.dangerouslyAllowAdditionalPlugins`, or supply them through `dangerouslyAllowAdditionalPlugins` when creating the generator directly. Plugins configured through `defaultPlugins` are also permitted. Generation stops if the MkDocs configuration cannot be read, parsed, or updated.

##### Minor Changes

- [`ee97130`](https://github.com/backstage/backstage/commit/ee97130): Added support for `techdocs.generator.pullOptions` when pulling the TechDocs generator Docker image from private registries that require authentication.

##### Patch Changes

- [`1711594`](https://github.com/backstage/backstage/commit/1711594): Fixed local TechDocs generation when temporary source paths resolve through filesystem aliases.
- [`c0ebaa7`](https://github.com/backstage/backstage/commit/c0ebaa7): chore(deps): bump `js-yaml` from 4.3.1 to 4.3.2
- [`e58d265`](https://github.com/backstage/backstage/commit/e58d265): Updated TechDocs generation to reject source trees containing symlinks that resolve outside the source directory.
- [`d13ad29`](https://github.com/backstage/backstage/commit/d13ad29): Improved MkDocs configuration handling for additional templates.
- [`e582b56`](https://github.com/backstage/backstage/commit/e582b56): Fixed AWS S3 publishing to paginate existing objects in order to properly remove all stale TechDocs files.
- [`2233af2`](https://github.com/backstage/backstage/commit/2233af2): Improved MkDocs configuration sanitization to cover additional nested configuration keys and theme options.
- [`4441911`](https://github.com/backstage/backstage/commit/4441911): Improved MkDocs configuration file handling.
- [`45cbd0a`](https://github.com/backstage/backstage/commit/45cbd0a): Improved validation of MkDocs configuration values during TechDocs generation.
- [`030331b`](https://github.com/backstage/backstage/commit/030331b): Improved file validation in the local TechDocs publisher during the publish step.

#### 1.16.0-next.1

##### Patch Changes

- [`1711594`](https://github.com/backstage/backstage/commit/1711594): Fixed local TechDocs generation when temporary source paths resolve through filesystem aliases.
- [`e582b56`](https://github.com/backstage/backstage/commit/e582b56): Fixed AWS S3 publishing to paginate existing objects in order to properly remove all stale TechDocs files.

#### 1.16.0-next.0

##### Minor Changes

- [`ee97130`](https://github.com/backstage/backstage/commit/ee97130): Added support for `techdocs.generator.pullOptions` when pulling the TechDocs generator Docker image from private registries that require authentication.

##### Patch Changes

- [`e58d265`](https://github.com/backstage/backstage/commit/e58d265): Updated TechDocs generation to reject source trees containing symlinks that resolve outside the source directory.
- [`d13ad29`](https://github.com/backstage/backstage/commit/d13ad29): Improved MkDocs configuration handling for additional templates.
- [`2233af2`](https://github.com/backstage/backstage/commit/2233af2): Improved MkDocs configuration sanitization to cover additional nested configuration keys and theme options.
- [`4441911`](https://github.com/backstage/backstage/commit/4441911): Improved MkDocs configuration file handling.
- [`45cbd0a`](https://github.com/backstage/backstage/commit/45cbd0a): Improved validation of MkDocs configuration values during TechDocs generation.
- [`030331b`](https://github.com/backstage/backstage/commit/030331b): Improved file validation in the local TechDocs publisher during the publish step.

### `@backstage/ui` (0.17.1 → [0.19.0](../../changelogs/@backstage/ui.md#0190))

#### 0.19.0

##### Minor Changes

- [`4e7a710`](https://github.com/backstage/backstage/commit/4e7a710): Updated React Aria dependencies to React Aria Components 1.22.0, React Aria 3.53.0, and React Stately 3.51.0. Existing Checkbox, Radio, and Switch implementations are retained.

  **Migration:**

  `MenuSection` no longer accepts `disabledKeys`. Move `disabledKeys` to `Menu` or set `isDisabled` on the affected `MenuItem` components.

  Programmatic clicks on Checkbox and Switch labels no longer toggle their selection. Target the input when activating these controls programmatically, and use a full pointer interaction when simulating label clicks in tests.

  **Affected components:** Checkbox, Menu, Switch

##### Patch Changes

- [`46659eb`](https://github.com/backstage/backstage/commit/46659eb): The `--bui-bg-app` token now follows the page's `color-scheme` until a theme mode is set. While the app loads, the page background then matches a dark theme instead of showing as light. Browsers without `light-dark()` support keep the light value until the theme mode is set, as before.
- [`6c9ed14`](https://github.com/backstage/backstage/commit/6c9ed14): Fixed `Combobox` keyboard selection while filtering. With `search`, or with `items` and no `search`, the arrow keys now move through the matching options only, and Enter selects the highlighted one. Screen readers also announce the number of matching options. As with a `Combobox` without `search`, opening the list with the button or on focus shows every option until the user types. With `search.filter`, Escape and blur now restore the label of the selected option even when the filter excludes it. In that case, the number of options announced to screen readers still counts the hidden selected option.

  **Affected components:** Combobox

- [`b313f2d`](https://github.com/backstage/backstage/commit/b313f2d): Added a `theme` CSS cascade layer between `components` and `utilities`. BUI leaves it empty: put your app's brand overrides in `@layer theme` to win over component styles without raising specificity, while utility props still take precedence. Existing styles are unaffected.

  If your app already declares its own layer named `theme`, its rules now sit below BUI's utility classes instead of above them.

#### 0.18.0

##### Minor Changes

- [`d07e99e`](https://github.com/backstage/backstage/commit/d07e99e): Updated BUI links to use the hosting application's client-side router, including relative destinations and the application's configured router base path, while preserving native browser navigation where required.

  **BREAKING**: Anchor-based components no longer accept the React Aria `render` prop. BUI now owns the underlying anchor so routing behavior remains consistent across application and plugin package versions.

  ListRow, Tag, and table Row now retain client-side navigation when application and plugin packages load separate React Aria copies. Their existing modifier-key, target, download, and link-metadata behavior is unchanged.

  **Migration:**

  Remove `render` props from ButtonLink, ComboboxItem, Link, MenuItem, MenuListBoxItem, SearchAutocompleteItem, SelectItem, and Tab. BUI now selects and renders the appropriate anchor or router link automatically.

  **Affected components:** ButtonLink, Card, ComboboxItem, Header, Link, ListRow, MenuItem, MenuListBoxItem, Row, SearchAutocompleteItem, SelectItem, Tab, Tag

##### Patch Changes

- [`736d84e`](https://github.com/backstage/backstage/commit/736d84e): Use locale-insensitive Unicode casing for consistent string handling across environments.

  **Affected components:** Avatar

- [`f914343`](https://github.com/backstage/backstage/commit/f914343): Prevent BUI styles from overriding document and native control line heights while preserving BUI component typography.
- [`947c612`](https://github.com/backstage/backstage/commit/947c612): Fixed `TablePagination` page-size controls to stay synchronized with controlled values and handle empty option lists without crashing.

  **Affected components:** `TablePagination`

- [`c435198`](https://github.com/backstage/backstage/commit/c435198): Fixed an issue where using `PluginHeader` with `FullPage` caused the page to be unexpectedly scrollable. The `--bui-header-height` CSS variable now correctly accounts for the header's `margin-bottom`, preventing the layout from overflowing the viewport.
- [`c0b26db`](https://github.com/backstage/backstage/commit/c0b26db): Open `Combobox` suggestions when the input receives focus by default.

  **Affected components:** Combobox

- [`0dd80f7`](https://github.com/backstage/backstage/commit/0dd80f7): Fixed pagination state handling in `useTable`, including initial offsets, shrinking complete datasets, controlled loading transitions, valid zero and empty cursors, cached error recovery, immediately resolving reloads, and unnecessary reloads when controlled callback identities change.

  **Affected components:** `useTable`

## Major version bumps

### `@backstage/plugin-catalog-react` (3.2.2 → [4.0.0-next.0](../../changelogs/@backstage/plugin-catalog-react.md#400-next0))

#### 3.3.0

##### Minor Changes

- [`6c74f3f`](https://github.com/backstage/backstage/commit/6c74f3f): Added `getCatalogQuery` to `EntityFilter`, which lets filters express their backend constraints as a filter predicate. This supports logical operators such as `$any` and `$not`, as well as matchers like `$hasPrefix`, that cannot be expressed with `getCatalogFilters`. All builtin filters now implement it, and `getCatalogFilters` is deprecated. If a filter implements both, only `getCatalogQuery` is used.

  The `EntityListProvider` and related components combine the predicates of all active filters into a `query`, and send it to the catalog backend alongside a `filter` built from any remaining legacy filters. When not paginating, entities are now fetched using `streamEntities` instead of `getEntities`, since the latter does not support predicate queries. Tests that mock `getEntities` to provide entities to an `EntityListProvider` need to mock `streamEntities` instead.

  This requires a catalog backend from Backstage release 1.49 or later, which added support for predicate queries.

  Since entities are now fetched using `queryEntities` also when not paginating, an `EntityOrderFilter` that orders by a field that some entities lack now excludes those entities from the result, consistent with paginated mode. Previously they were placed last.

  Some builtin filters became more precise as part of this change:

  - `EntityTagFilter` with multiple tags now requires all of them on the backend, matching its frontend behavior.
  - `EntityUserFilter.starred` matches the full starred entity refs rather than just their names, and the starred count is computed by the backend.

##### Patch Changes

- [`c162b94`](https://github.com/backstage/backstage/commit/c162b94): Fixed the catalog entity list re-writing the URL on every render, which spammed `history.replaceState` and crashed Safari with a `SecurityError`. The URL is now only updated when it actually changes.

#### 3.3.0-next.2

##### Minor Changes

- [`6c74f3f`](https://github.com/backstage/backstage/commit/6c74f3f): Added `getCatalogQuery` to `EntityFilter`, which lets filters express their backend constraints as a filter predicate. This supports logical operators such as `$any` and `$not`, as well as matchers like `$hasPrefix`, that cannot be expressed with `getCatalogFilters`. All builtin filters now implement it, and `getCatalogFilters` is deprecated. If a filter implements both, only `getCatalogQuery` is used.

  The `EntityListProvider` and related components combine the predicates of all active filters into a `query`, and send it to the catalog backend alongside a `filter` built from any remaining legacy filters. When not paginating, entities are now fetched using `streamEntities` instead of `getEntities`, since the latter does not support predicate queries. Tests that mock `getEntities` to provide entities to an `EntityListProvider` need to mock `streamEntities` instead.

  This requires a catalog backend from Backstage release 1.49 or later, which added support for predicate queries.

  Since entities are now fetched using `queryEntities` also when not paginating, an `EntityOrderFilter` that orders by a field that some entities lack now excludes those entities from the result, consistent with paginated mode. Previously they were placed last.

  Some builtin filters became more precise as part of this change:

  - `EntityTagFilter` with multiple tags now requires all of them on the backend, matching its frontend behavior.
  - `EntityUserFilter.starred` matches the full starred entity refs rather than just their names, and the starred count is computed by the backend.

#### 3.2.4-next.1

##### Patch Changes

- [`c162b94`](https://github.com/backstage/backstage/commit/c162b94): Fixed the catalog entity list re-writing the URL on every render, which spammed `history.replaceState` and crashed Safari with a `SecurityError`. The URL is now only updated when it actually changes.

#### 3.2.3

##### Patch Changes

- [`736d84e`](https://github.com/backstage/backstage/commit/736d84e): Use locale-insensitive Unicode casing for consistent string handling across environments.
- [`a7b14b5`](https://github.com/backstage/backstage/commit/a7b14b5): Fixed `EntityOwnerPicker` crashing with `Entity reference "<name>" had missing or empty kind` when the `owners` query parameter contains humanized entity refs, as produced by the `OwnershipCard` links in `@backstage/plugin-org`.

  Query parameters were stored as-is in the initial state and only converted to full entity refs by an effect, which runs after the first render. That first render passed the raw value to the entity presentation API, whose `parseEntityRef` call rejects a ref without a kind. The same raw value was also sent to `catalogApi.getEntitiesByRefs` on mount, and made the option checkboxes render unselected until the effect ran.

  The query parameters are now normalized through `EntityOwnerFilter` when the state is initialized, matching what the existing effect already did and what the `filters` code path already produced.

- [`bf7e890`](https://github.com/backstage/backstage/commit/bf7e890): Added the missing Material UI dependency used by catalog popovers.

#### 3.2.3-next.1

##### Patch Changes

- [`bf7e890`](https://github.com/backstage/backstage/commit/bf7e890): Added the missing Material UI dependency used by catalog popovers.

### `@backstage/plugin-scaffolder-react` (2.0.3 → [3.0.0-next.0](../../changelogs/@backstage/plugin-scaffolder-react.md#300-next0))

#### 3.0.0-next.0

##### Minor Changes

- [`3fe82f6`](https://github.com/backstage/backstage/commit/3fe82f6): Added a `ScaffolderTemplateFilterBlueprint` that lets apps filter the new frontend system's template list using identity, catalog, or other viewer-specific state.

##### Patch Changes

- [`1c461ca`](https://github.com/backstage/backstage/commit/1c461ca): Fixed BUI array item headings to use the item schema title and honor an explicit item `ui:title` without adding a numeric suffix. Untitled items retain the numbered fallback.

#### 2.1.0

##### Minor Changes

- [`5ff93bf`](https://github.com/backstage/backstage/commit/5ff93bf): Added functionality to register a Template Outputs Component in the new frontend system.

##### Patch Changes

- [`736d84e`](https://github.com/backstage/backstage/commit/736d84e): Use locale-insensitive Unicode casing for consistent string handling across environments.
- [`ffaca06`](https://github.com/backstage/backstage/commit/ffaca06): Fixed several issues with scaffolder task event stream reconnection: retry timers are now properly cancelled on cleanup, concurrent reconnect attempts are guarded against, and tab visibility changes reconnect the stream using the last seen event cursor without re-fetching the task.
- [`7c1019c`](https://github.com/backstage/backstage/commit/7c1019c): Fixed the scaffolder wizard not scrolling to the top on step change when the app uses the new frontend system (no `<main>` element).

#### 2.1.0-next.1

##### Patch Changes

- [`7c1019c`](https://github.com/backstage/backstage/commit/7c1019c): Fixed the scaffolder wizard not scrolling to the top on step change when the app uses the new frontend system (no `<main>` element).

#### 2.1.0-next.0

##### Minor Changes

- [`5ff93bf`](https://github.com/backstage/backstage/commit/5ff93bf): Added functionality to register a Template Outputs Component in the new frontend system.

## 0.x minor version bumps

### `@backstage/backend-defaults` (0.17.8 → [0.18.2-next.0](../../changelogs/@backstage/backend-defaults.md#0182-next0))

#### 0.18.2-next.0

##### Patch Changes

- [`80cc892`](https://github.com/backstage/backstage/commit/80cc892): Removed the runtime dependency on `@backstage/cli-node`, which was only used for types. Backends no longer install the CLI tooling packages through `@backstage/backend-defaults`.
- [`918ca98`](https://github.com/backstage/backstage/commit/918ca98): Updated dependency `jose` to `^6.1.0`. Existing ES256 token issuance and verification are unchanged. ML-DSA algorithms can be used when the runtime supports them.

#### 0.18.1

##### Patch Changes

- [`c478470`](https://github.com/backstage/backstage/commit/c478470): Added a service-authenticated action registry status endpoint that reports whether a plugin provides actions without exposing action metadata.
- [`f6054ac`](https://github.com/backstage/backstage/commit/f6054ac): Backends created with `createBackend` now provide the experimental connections service by default. Custom backends can install `connectionsServiceFactory` from `@backstage/backend-defaults/alpha`.
- [`e956084`](https://github.com/backstage/backstage/commit/e956084): Added an `instanceId` option to `createBackend`, allowing deployments to use an externally provided backend instance identifier. Each backend instance uses a random UUID by default.
- [`1939ded`](https://github.com/backstage/backstage/commit/1939ded): Added bounded retries for transient failures while initializing Cloud SQL database connections.
- [`a6bc5e4`](https://github.com/backstage/backstage/commit/a6bc5e4): Stopped issuing periodic per-plugin database keepalive queries by default and changed the default minimum PostgreSQL and MySQL connection pool size to zero. Idle connections can now be retired after the configured timeout, while explicitly configured pool minimums are preserved. Set `backend.database.keepalive: true` to continue issuing the periodic queries.
- [`bd1ff39`](https://github.com/backstage/backstage/commit/bd1ff39): Fixed AWS RDS IAM authentication tokens being reused after their signing credentials expire, which could cause database connection failures when using temporary AWS credentials.
- [`6887ecc`](https://github.com/backstage/backstage/commit/6887ecc): Updated dependency `infinispan` to `^0.16.0`.
- [`495ef24`](https://github.com/backstage/backstage/commit/495ef24): Added support for `backend.logger.redactAllowlist` configuration option, which allows specific secret values to pass through log redaction when they are known to be safe to log.

#### 0.18.1-next.3

##### Patch Changes

- [`f6054ac`](https://github.com/backstage/backstage/commit/f6054ac): Backends created with `createBackend` now provide the experimental connections service by default. Custom backends can install `connectionsServiceFactory` from `@backstage/backend-defaults/alpha`.
- [`bd1ff39`](https://github.com/backstage/backstage/commit/bd1ff39): Fixed AWS RDS IAM authentication tokens being reused after their signing credentials expire, which could cause database connection failures when using temporary AWS credentials.

#### 0.18.1-next.2

##### Patch Changes

- [`a6bc5e4`](https://github.com/backstage/backstage/commit/a6bc5e4): Stopped issuing periodic per-plugin database keepalive queries by default and changed the default minimum PostgreSQL and MySQL connection pool size to zero. Idle connections can now be retired after the configured timeout, while explicitly configured pool minimums are preserved. Set `backend.database.keepalive: true` to continue issuing the periodic queries.

#### 0.18.1-next.1

##### Patch Changes

- [`c478470`](https://github.com/backstage/backstage/commit/c478470): Added a service-authenticated action registry status endpoint that reports whether a plugin provides actions without exposing action metadata.
- [`e956084`](https://github.com/backstage/backstage/commit/e956084): Added an `instanceId` option to `createBackend`, allowing deployments to use an externally provided backend instance identifier. Each backend instance uses a random UUID by default.
- [`1939ded`](https://github.com/backstage/backstage/commit/1939ded): Added bounded retries for transient failures while initializing Cloud SQL database connections.
- [`6887ecc`](https://github.com/backstage/backstage/commit/6887ecc): Updated dependency `infinispan` to `^0.16.0`.

#### 0.18.0

##### Minor Changes

- [`2e07985`](https://github.com/backstage/backstage/commit/2e07985): Add schemaPrefix configuration for pluginDivisionMode: schema. Allows prefixing PostgreSQL schema names to avoid conflicts with existing schemas.

##### Patch Changes

- [`fe6ace6`](https://github.com/backstage/backstage/commit/fe6ace6): Fixed `AwsS3UrlReader` and `AwsCodeCommitUrlReader` to resolve account-specific AWS credentials when an assume role ARN is configured, enabling support for `webIdentityTokenFile` and `accountDefaults` in environments without default AWS credentials.
- [`45d760b`](https://github.com/backstage/backstage/commit/45d760b): Improve action handling consistency.
- [`8d71644`](https://github.com/backstage/backstage/commit/8d71644): Reduced PostgreSQL connection churn during backend startup when many plugins initialize databases or schemas.
- [`416be1b`](https://github.com/backstage/backstage/commit/416be1b): Updated Harness URL reading to validate cross-origin redirect destinations
  against `backend.reading.allow`.
- [`c59472e`](https://github.com/backstage/backstage/commit/c59472e): Plugin route registration now rejects paths that differ only by letter casing,
  and HTTP credentials are resolved independently for each plugin service instance.
- [`5aac521`](https://github.com/backstage/backstage/commit/5aac521): Improved service credential handling during plugin-to-plugin delegation.
- [`61449ae`](https://github.com/backstage/backstage/commit/61449ae): Reduced PostgreSQL startup connections when multiple plugins share a database by reusing the database existence check.
- [`55f30b8`](https://github.com/backstage/backstage/commit/55f30b8): Reduced scheduler database polling overhead by batching readiness checks for global tasks registered by each plugin into one query per poll cycle on each backend instance.
- [`8b3c83e`](https://github.com/backstage/backstage/commit/8b3c83e): Improved input validation and path handling for cloud storage URL readers.
- [`61d97c0`](https://github.com/backstage/backstage/commit/61d97c0): Improved input validation for cloud storage URL readers.
- [`e895def`](https://github.com/backstage/backstage/commit/e895def): Fixed handling of GitLab URLs for instances configured with a relative base path.
- [`f6f339e`](https://github.com/backstage/backstage/commit/f6f339e): Fixed redundant signing-key requests when concurrently authenticating the first incoming requests from a plugin. Concurrent requests now share the same key cache, including when retrying after an initial fetch failure.
- [`e13e278`](https://github.com/backstage/backstage/commit/e13e278): Updated URL reader allow list matching so configured paths match either the exact path or paths below it at a segment boundary.
- [`e3b587c`](https://github.com/backstage/backstage/commit/e3b587c): Improve authentication reliability during signing key rotation by performing budgeted JWKS reloads when a newly published key is requested during the remote key set cooldown.

#### 0.17.9-next.1

##### Patch Changes

- [`55f30b8`](https://github.com/backstage/backstage/commit/55f30b8): Reduced scheduler database polling overhead by batching readiness checks for global tasks registered by each plugin into one query per poll cycle on each backend instance.

#### 0.17.9-next.0

##### Patch Changes

- [`45d760b`](https://github.com/backstage/backstage/commit/45d760b): Improve action handling consistency.
- [`8d71644`](https://github.com/backstage/backstage/commit/8d71644): Reduced PostgreSQL connection churn during backend startup when many plugins initialize databases or schemas.
- [`416be1b`](https://github.com/backstage/backstage/commit/416be1b): Updated Harness URL reading to validate cross-origin redirect destinations
  against `backend.reading.allow`.
- [`5aac521`](https://github.com/backstage/backstage/commit/5aac521): Improved service credential handling during plugin-to-plugin delegation.
- [`61449ae`](https://github.com/backstage/backstage/commit/61449ae): Reduced PostgreSQL startup connections when multiple plugins share a database by reusing the database existence check.
- [`8b3c83e`](https://github.com/backstage/backstage/commit/8b3c83e): Improved input validation and path handling for cloud storage URL readers.
- [`61d97c0`](https://github.com/backstage/backstage/commit/61d97c0): Improved input validation for cloud storage URL readers.
- [`e895def`](https://github.com/backstage/backstage/commit/e895def): Fixed handling of GitLab URLs for instances configured with a relative base path.
- [`e13e278`](https://github.com/backstage/backstage/commit/e13e278): Updated URL reader allow list matching so configured paths match either the exact path or paths below it at a segment boundary.
- [`e3b587c`](https://github.com/backstage/backstage/commit/e3b587c): Improve authentication reliability during signing key rotation by performing budgeted JWKS reloads when a newly published key is requested during the remote key set cooldown.

### `@backstage/plugin-catalog-backend-module-github` (0.13.5 → [0.14.2-next.0](../../changelogs/@backstage/plugin-catalog-backend-module-github.md#0142-next0))

#### 0.14.0

##### Minor Changes

- [`6ecff59`](https://github.com/backstage/backstage/commit/6ecff59): The GitHub multi-org entity provider now logs a clear warning and aborts ingestion when no GitHub App installation is found for an org, instead of failing with a confusing rate-limit or authentication error. This prevents silent deletion of existing catalog entities.

##### Patch Changes

- [`736d84e`](https://github.com/backstage/backstage/commit/736d84e): Use locale-insensitive Unicode casing for consistent string handling across environments.

#### 0.14.0-next.0

##### Minor Changes

- [`6ecff59`](https://github.com/backstage/backstage/commit/6ecff59): The GitHub multi-org entity provider now logs a clear warning and aborts ingestion when no GitHub App installation is found for an org, instead of failing with a confusing rate-limit or authentication error. This prevents silent deletion of existing catalog entities.

### `@backstage/plugin-notifications` (0.5.20 → [0.6.2-next.0](../../changelogs/@backstage/plugin-notifications.md#062-next0))

#### 0.6.1

##### Patch Changes

- [`4e7a710`](https://github.com/backstage/backstage/commit/4e7a710): Updated React Aria dependencies to the October 2026 release.
- [`298f908`](https://github.com/backstage/backstage/commit/298f908): Replaced the unmaintained `react-relative-time` dependency with an internal component based on `luxon`.

#### 0.6.1-next.1

##### Patch Changes

- [`4e7a710`](https://github.com/backstage/backstage/commit/4e7a710): Updated React Aria dependencies to the October 2026 release.

#### 0.6.0

##### Minor Changes

- [`cd4a9c7`](https://github.com/backstage/backstage/commit/cd4a9c7): Added an unread notifications home page card and NFS home widget.

##### Patch Changes

- [`736d84e`](https://github.com/backstage/backstage/commit/736d84e): Use locale-insensitive Unicode casing for consistent string handling across environments.
- [`b31afcf`](https://github.com/backstage/backstage/commit/b31afcf): Fixed circular dependency warnings when building the notification settings UI.

#### 0.5.21-next.1

##### Patch Changes

- [`b31afcf`](https://github.com/backstage/backstage/commit/b31afcf): Fixed circular dependency warnings when building the notification settings UI.

### `@backstage/plugin-org` (0.7.8 → [0.8.1-next.0](../../changelogs/@backstage/plugin-org.md#081-next0))

#### 0.8.0

##### Minor Changes

- [`1557a8c`](https://github.com/backstage/backstage/commit/1557a8c): Added a swappable `UserAvatar` component and wired org plugin surfaces to use it for user profile pictures.

#### 0.8.0-next.1

##### Minor Changes

- [`1557a8c`](https://github.com/backstage/backstage/commit/1557a8c): Added a swappable `UserAvatar` component and wired org plugin surfaces to use it for user profile pictures.

#### 0.7.9

##### Patch Changes

- [`736d84e`](https://github.com/backstage/backstage/commit/736d84e): Use locale-insensitive Unicode casing for consistent string handling across environments.
- [`fe0ec65`](https://github.com/backstage/backstage/commit/fe0ec65): Fixed ownership card catalog links to filter by stable entity references instead of display titles.

### `@backstage/plugin-scaffolder-backend-module-gitlab` (0.11.10 → [0.12.2-next.0](../../changelogs/@backstage/plugin-scaffolder-backend-module-gitlab.md#0122-next0))

#### 0.12.2-next.0

##### Patch Changes

- [`ae86338`](https://github.com/backstage/backstage/commit/ae86338): Added GitLab branch autocompletion to RepoBranchPicker using user SCM credentials.
- [`ed8e58f`](https://github.com/backstage/backstage/commit/ed8e58f): Fixed `publish:gitlab:merge-request` and `gitlab:repo:push` failing with "A file with this name already exists" when `commitAction` is `auto` and the repository file list cannot be fetched, for example when the request times out on a large repository. The actions now check each file individually in that case, instead of treating every file as new.

#### 0.12.1

##### Patch Changes

- [`06128be`](https://github.com/backstage/backstage/commit/06128be): Throw a `ConflictError` with a clear message when `publish:gitlab` is called and the target repository already exists, instead of letting the GitLab API return a `GitbeakerRequestError` with a raw JSON body such as `{"name":["has already been taken"]}`.
- [`fe51d40`](https://github.com/backstage/backstage/commit/fe51d40): Added a secure `variableKey` input to `gitlab:projectAccessToken:create` and `gitlab:projectDeployToken:create` actions. When provided, the generated token is stored directly as a masked GitLab CI/CD variable instead of being exposed in task outputs and checkpoint state. The raw token outputs are now deprecated when `variableKey` is not used.

#### 0.12.1-next.2

##### Patch Changes

- [`06128be`](https://github.com/backstage/backstage/commit/06128be): Throw a `ConflictError` with a clear message when `publish:gitlab` is called and the target repository already exists, instead of letting the GitLab API return a `GitbeakerRequestError` with a raw JSON body such as `{"name":["has already been taken"]}`.

#### 0.12.0

##### Minor Changes

- [`5c14f42`](https://github.com/backstage/backstage/commit/5c14f42): The `gitlab:issues:create` action now accepts a full project path (e.g. `group/sub-group/project`) for `projectId`, and `projectId` is optional — when omitted the project is derived from `repoUrl` (matching the behaviour of `gitlab:merge-request`).

##### Patch Changes

- [`736d84e`](https://github.com/backstage/backstage/commit/736d84e): Use locale-insensitive Unicode casing for consistent string handling across environments.
- [`bbba6b5`](https://github.com/backstage/backstage/commit/bbba6b5): Added support for requiring user-provided credentials for GitLab mutation actions when `scaffolder.requireScmUserCredentials` is enabled.
- [`20595f0`](https://github.com/backstage/backstage/commit/20595f0): The `gitlab:projectVariable:create` action no longer includes the variable value in its checkpoint key, preventing secret values from being persisted in scaffolder task state. The `gitlab:pipeline:trigger` action has been refactored so that the temporary pipeline trigger token is never serialized into checkpoint state.
- [`4740660`](https://github.com/backstage/backstage/commit/4740660): Sped up `publish:gitlab:merge-request` and `gitlab:repo:push` by drastically reducing the number
  of GitLab API requests they make.

  Under the default `commitAction: 'auto'`, both actions previously downloaded the contents of every
  file already present on the target branch in order to work out which ones had actually changed.
  That information is available from the repository listing they already fetch, so the comparison is
  now done locally and those per-file requests are gone. The listing itself is also fetched in larger
  pages.

  For a merge request against a repository of a few hundred files this cuts the number of requests
  from roughly 300 to under ten, taking a step that took 5-15 seconds against a self-hosted GitLab
  down to about 3 seconds. Which files are created, updated or skipped is unchanged, including for
  repositories using git sha256 object format.

- [`3c7c082`](https://github.com/backstage/backstage/commit/3c7c082): Fixed `gitlab:repo:push` failing with `400 Bad request - Provide at least one action` when the workspace has no file changes to commit (e.g. re-running a template against an already up-to-date branch). The action now detects an empty action list, skips the commit API call, and logs a warning whenever `allowEmpty` is not true (covering both the default of unset and an explicit `false`). The `commitHash` output is omitted in this no-op case and is now declared optional. Pass `allowEmpty: true` to retain the previous behavior of forwarding an empty commit to GitLab.
- [`cd77db3`](https://github.com/backstage/backstage/commit/cd77db3): Added an `autoMerge` boolean input to the `publish:gitlab:merge-request` scaffolder action. When set to `true`, the merge request is automatically merged once all merge checks succeed, using GitLab's auto-merge feature.

#### 0.11.11-next.2

##### Patch Changes

- [`20595f0`](https://github.com/backstage/backstage/commit/20595f0): The `gitlab:projectVariable:create` action no longer includes the variable value in its checkpoint key, preventing secret values from being persisted in scaffolder task state. The `gitlab:pipeline:trigger` action has been refactored so that the temporary pipeline trigger token is never serialized into checkpoint state.
- [`4740660`](https://github.com/backstage/backstage/commit/4740660): Sped up `publish:gitlab:merge-request` and `gitlab:repo:push` by drastically reducing the number
  of GitLab API requests they make.

  Under the default `commitAction: 'auto'`, both actions previously downloaded the contents of every
  file already present on the target branch in order to work out which ones had actually changed.
  That information is available from the repository listing they already fetch, so the comparison is
  now done locally and those per-file requests are gone. The listing itself is also fetched in larger
  pages.

  For a merge request against a repository of a few hundred files this cuts the number of requests
  from roughly 300 to under ten, taking a step that took 5-15 seconds against a self-hosted GitLab
  down to about 3 seconds. Which files are created, updated or skipped is unchanged, including for
  repositories using git sha256 object format.

#### 0.11.11-next.1

##### Patch Changes

- [`bbba6b5`](https://github.com/backstage/backstage/commit/bbba6b5): Added support for requiring user-provided credentials for GitLab mutation actions when `scaffolder.requireScmUserCredentials` is enabled.
- [`cd77db3`](https://github.com/backstage/backstage/commit/cd77db3): Added an `autoMerge` boolean input to the `publish:gitlab:merge-request` scaffolder action. When set to `true`, the merge request is automatically merged once all merge checks succeed, using GitLab's auto-merge feature.

## 0.0.x patch version bumps

### `@backstage/plugin-kubernetes-cluster` (0.0.40 → [0.0.43-next.0](../../changelogs/@backstage/plugin-kubernetes-cluster.md#0043-next0))

#### 0.0.43-next.0

##### Patch Changes

- [`ca14116`](https://github.com/backstage/backstage/commit/ca14116): Moved `kubernetes-models` and `@kubernetes-models/apimachinery` to dev dependencies, since they are only used for types. Backends no longer install `kubernetes-models` through `@backstage/plugin-kubernetes-common`.

### `@backstage/plugin-signals` (0.0.34 → [0.0.37-next.0](../../changelogs/@backstage/plugin-signals.md#0037-next0))

#### 0.0.36

##### Patch Changes

- [`b8e865b`](https://github.com/backstage/backstage/commit/b8e865b): The signals client now shares one WebSocket connection across simultaneous subscriptions and does not connect or retry when no identity token is available.

#### 0.0.36-next.1

##### Patch Changes

- [`b8e865b`](https://github.com/backstage/backstage/commit/b8e865b): The signals client now shares one WebSocket connection across simultaneous subscriptions and does not connect or retry when no identity token is available.

### `@backstage/release-manifests` (0.0.14 → [0.0.15](../../changelogs/@backstage/release-manifests.md#0015))

#### 0.0.15

##### Patch Changes

- [`5834faa`](https://github.com/backstage/backstage/commit/5834faa): Release manifests now include requirements such as supported Node.js versions when that information is available from the release.

## 0.x patch version bumps

### `@backstage/backend-dynamic-feature-service` (0.8.6 → [0.8.9-next.0](../../changelogs/@backstage/backend-dynamic-feature-service.md#089-next0))

#### 0.8.9-next.0

##### Patch Changes

- [`c999b77`](https://github.com/backstage/backstage/commit/c999b77): Dynamic backend plugins can now require the packages they share with the backend when those packages are not in the root `node_modules`, as with the pnpm `isolated` node linker. They are found through the backend package and through this package. With the default pnpm hoisting, this includes the packages that pnpm hoists into `node_modules/.pnpm/node_modules`. With `hoist: false`, only the direct dependencies of the backend package and of this package are found. Everything that was searched before is still searched first, so a module that was found before is found in the same place. The exception is plugins inside the Backstage root on Windows, which did not search the root `node_modules` before, other than through `NODE_PATH`. It is now searched in the same order as on other platforms.

#### 0.8.8

##### Patch Changes

- [`786a8ea`](https://github.com/backstage/backstage/commit/786a8ea): Corrected the `schemaLocator` documentation to identify `dist/.config-schema.json` as the default dynamic-plugin config-schema path.
- [`b9c9dd2`](https://github.com/backstage/backstage/commit/b9c9dd2): Internal refactor of dynamic backend plugin alpha-to-main entrypoint loading. No intended behavior change.

#### 0.8.8-next.1

##### Patch Changes

- [`786a8ea`](https://github.com/backstage/backstage/commit/786a8ea): Corrected the `schemaLocator` documentation to identify `dist/.config-schema.json` as the default dynamic-plugin config-schema path.
- [`b9c9dd2`](https://github.com/backstage/backstage/commit/b9c9dd2): Internal refactor of dynamic backend plugin alpha-to-main entrypoint loading. No intended behavior change.

#### 0.8.7

##### Patch Changes

- [`064c2de`](https://github.com/backstage/backstage/commit/064c2de): Updated the Module Federation dependencies to versions that avoid known security vulnerabilities.

#### 0.8.7-next.2

##### Patch Changes

- [`064c2de`](https://github.com/backstage/backstage/commit/064c2de): Updated the Module Federation dependencies to versions that avoid known security vulnerabilities.

### `@backstage/backend-openapi-utils` (0.7.1 → [0.7.4-next.0](../../changelogs/@backstage/backend-openapi-utils.md#074-next0))

#### 0.7.3

##### Patch Changes

- [`812225c`](https://github.com/backstage/backstage/commit/812225c): Fixed the OpenAPI validation test server wrapper to support `supertest` 7.3 by returning a standard server address for the validation proxy.

#### 0.7.3-next.2

##### Patch Changes

- [`812225c`](https://github.com/backstage/backstage/commit/812225c): Fixed the OpenAPI validation test server wrapper to support `supertest` 7.3 by returning a standard server address for the validation proxy.

#### 0.7.2

##### Patch Changes

- [`736d84e`](https://github.com/backstage/backstage/commit/736d84e): Use locale-insensitive Unicode casing for consistent string handling across environments.
- [`bf1f82d`](https://github.com/backstage/backstage/commit/bf1f82d): Added the required OpenAPI types dependency for Swagger Parser.

#### 0.7.2-next.0

##### Patch Changes

- [`bf1f82d`](https://github.com/backstage/backstage/commit/bf1f82d): Added the required OpenAPI types dependency for Swagger Parser.

### `@backstage/cli` (0.36.5 → [0.36.8-next.0](../../changelogs/@backstage/cli.md#0368-next0))

#### 0.36.7

##### Patch Changes

- [`933e50e`](https://github.com/backstage/backstage/commit/933e50e): The ESLint configuration for packages with the `common-library` role now reports named imports from `lodash`, such as `import { trimEnd } from 'lodash'`. Common libraries are published with an ESM build, and these imports cause that build to fail when imported from ESM projects in Node.js. Use `import lodash from 'lodash'` instead.
- [`36e3f24`](https://github.com/backstage/backstage/commit/36e3f24): Updated the test runner to use the latest Jest 30 releases.

#### 0.36.7-next.0

##### Patch Changes

- [`36e3f24`](https://github.com/backstage/backstage/commit/36e3f24): Updated the test runner to use the latest Jest 30 releases.

#### 0.36.6

##### Patch Changes

- [`89743dc`](https://github.com/backstage/backstage/commit/89743dc): Replaced the deprecated dependency used by `repo list-deprecations` with the equivalent TypeScript ESLint rule.

#### 0.36.6-next.1

##### Patch Changes

- [`89743dc`](https://github.com/backstage/backstage/commit/89743dc): Replaced the deprecated dependency used by `repo list-deprecations` with the equivalent TypeScript ESLint rule.

### `@backstage/cli-common` (0.3.0 → [0.3.2](../../changelogs/@backstage/cli-common.md#032))

#### 0.3.1

##### Patch Changes

- [`736d84e`](https://github.com/backstage/backstage/commit/736d84e): Use locale-insensitive Unicode casing for consistent string handling across environments.

### `@backstage/cli-defaults` (0.1.5 → [0.1.8-next.0](../../changelogs/@backstage/cli-defaults.md#018-next0))

#### 0.1.6

##### Patch Changes

- [`de957f6`](https://github.com/backstage/backstage/commit/de957f6): Added `@backstage/cli-module-package-manager-yarn` with `backstage-cli pm
verify-patches` to validate Yarn patch references, local patch files,
  lockfile consistency, and patched Backstage package versions against the
  selected Backstage release. The command is included in
  `@backstage/cli-defaults`.

#### 0.1.6-next.1

##### Patch Changes

- [`de957f6`](https://github.com/backstage/backstage/commit/de957f6): Added `@backstage/cli-module-package-manager-yarn` with `backstage-cli pm
verify-patches` to validate Yarn patch references, local patch files,
  lockfile consistency, and patched Backstage package versions against the
  selected Backstage release. The command is included in
  `@backstage/cli-defaults`.

### `@backstage/cli-module-actions` (0.1.3 → [0.1.5-next.0](../../changelogs/@backstage/cli-module-actions.md#015-next0))

#### 0.1.4

##### Patch Changes

- [`d73df15`](https://github.com/backstage/backstage/commit/d73df15): The `actions list` command now returns partial results when some plugin sources fail, instead of failing entirely. Failed sources are reported as warnings.

### `@backstage/cli-module-auth` (0.1.4 → [0.1.6-next.0](../../changelogs/@backstage/cli-module-auth.md#016-next0))

#### 0.1.6-next.0

##### Patch Changes

- [`4d94005`](https://github.com/backstage/backstage/commit/4d94005): Fixed `auth logout` so that it revokes the refresh token on the server. Previously the revocation request was rejected because it did not identify the CLI client, which left the session valid until it expired.

#### 0.1.5

##### Patch Changes

- [`2a83a41`](https://github.com/backstage/backstage/commit/2a83a41): Switched to version 4 of `zod` for internal validation.

### `@backstage/cli-module-build` (0.1.7 → [0.1.10-next.0](../../changelogs/@backstage/cli-module-build.md#0110-next0))

#### 0.1.9

##### Patch Changes

- [`cc4ef47`](https://github.com/backstage/backstage/commit/cc4ef47): Restored the default exclusion of `node_modules` from test coverage for this package.
- [`2ece167`](https://github.com/backstage/backstage/commit/2ece167): Updated dependency `webpack` to `~5.111.0`.
- [`f163298`](https://github.com/backstage/backstage/commit/f163298): Improved code splitting for frontend module federation remotes to reduce unnecessary downloads of unrelated lazy components from the same dependency scope. Shared dependencies and workspace code are extracted across lazy boundaries when the resulting shared chunk meets the size threshold. Regular application builds are unchanged.

#### 0.1.9-next.2

##### Patch Changes

- [`cc4ef47`](https://github.com/backstage/backstage/commit/cc4ef47): Restored the default exclusion of `node_modules` from test coverage for this package.
- [`f163298`](https://github.com/backstage/backstage/commit/f163298): Improved code splitting for frontend module federation remotes to reduce unnecessary downloads of unrelated lazy components from the same dependency scope. Shared dependencies and workspace code are extracted across lazy boundaries when the resulting shared chunk meets the size threshold. Regular application builds are unchanged.

#### 0.1.9-next.1

##### Patch Changes

- [`2ece167`](https://github.com/backstage/backstage/commit/2ece167): Updated dependency `webpack` to `~5.111.0`.

#### 0.1.8

##### Patch Changes

- [`064c2de`](https://github.com/backstage/backstage/commit/064c2de): Updated the Module Federation dependencies to versions that avoid known security vulnerabilities.
- [`96badbc`](https://github.com/backstage/backstage/commit/96badbc): Fixed a bug where plugin packages installed through feature discovery were loaded before the app's own code ran. This could cause bootstrap-order-sensitive setup code in the app, such as configuring MUI 5's class name prefix, to be skipped if a discovered plugin's dependencies loaded MUI 5 components first. Discovered plugin packages are now loaded after the app's own code instead.
- [`b2b7568`](https://github.com/backstage/backstage/commit/b2b7568): Significantly improve the performance of `build-workspace` when packaging many Backstage packages.
- [`277a125`](https://github.com/backstage/backstage/commit/277a125): Fixed declaration bundling of imports that use the `node:` built-in module prefix.

#### 0.1.8-next.2

##### Patch Changes

- [`064c2de`](https://github.com/backstage/backstage/commit/064c2de): Updated the Module Federation dependencies to versions that avoid known security vulnerabilities.
- [`96badbc`](https://github.com/backstage/backstage/commit/96badbc): Fixed a bug where plugin packages installed through feature discovery were loaded before the app's own code ran. This could cause bootstrap-order-sensitive setup code in the app, such as configuring MUI 5's class name prefix, to be skipped if a discovered plugin's dependencies loaded MUI 5 components first. Discovered plugin packages are now loaded after the app's own code instead.

#### 0.1.8-next.1

##### Patch Changes

- [`277a125`](https://github.com/backstage/backstage/commit/277a125): Fixed declaration bundling of imports that use the `node:` built-in module prefix.

#### 0.1.8-next.0

##### Patch Changes

- [`b2b7568`](https://github.com/backstage/backstage/commit/b2b7568): Significantly improve the performance of `build-workspace` when packaging many Backstage packages.

### `@backstage/cli-module-maintenance` (0.1.4 → [0.1.7-next.0](../../changelogs/@backstage/cli-module-maintenance.md#017-next0))

#### 0.1.5

##### Patch Changes

- [`89743dc`](https://github.com/backstage/backstage/commit/89743dc): Replaced the deprecated dependency used by `repo list-deprecations` with the equivalent TypeScript ESLint rule.

#### 0.1.5-next.0

##### Patch Changes

- [`89743dc`](https://github.com/backstage/backstage/commit/89743dc): Replaced the deprecated dependency used by `repo list-deprecations` with the equivalent TypeScript ESLint rule.

### `@backstage/cli-module-new` (0.1.6 → [0.1.9-next.0](../../changelogs/@backstage/cli-module-new.md#019-next0))

#### 0.1.8

##### Patch Changes

- [`e4597ce`](https://github.com/backstage/backstage/commit/e4597ce): Updated the `plugin-web-library` template to use `@backstage/ui` instead of the deprecated `@material-ui/core`.
- [`b717df2`](https://github.com/backstage/backstage/commit/b717df2): Switched to version 4 of `zod` for internal validation. Validation errors for invalid templates now use the updated, more descriptive `zod` wording.

#### 0.1.8-next.1

##### Patch Changes

- [`e4597ce`](https://github.com/backstage/backstage/commit/e4597ce): Updated the `plugin-web-library` template to use `@backstage/ui` instead of the deprecated `@material-ui/core`.

#### 0.1.7

##### Patch Changes

- [`33c8190`](https://github.com/backstage/backstage/commit/33c8190): Updated the frontend plugin templates to use MSW 2 for generated tests.
- [`4cba335`](https://github.com/backstage/backstage/commit/4cba335): Fixes published entry point configurations so it can be imported reliably in Jest/Node resolution.

#### 0.1.7-next.0

##### Patch Changes

- [`4cba335`](https://github.com/backstage/backstage/commit/4cba335): Fixes published entry point configurations so it can be imported reliably in Jest/Node resolution.

### `@backstage/cli-module-test-jest` (0.1.5 → [0.1.8-next.0](../../changelogs/@backstage/cli-module-test-jest.md#018-next0))

#### 0.1.7

##### Patch Changes

- [`8747376`](https://github.com/backstage/backstage/commit/8747376): `jest-cli`, `jest-runtime` and the default Node.js test environment are now loaded through the installed `jest` package, so tests also run with strict `node_modules` layouts. An unsupported Jest version, or a missing `jest`, now fails with a clear error instead of a module resolution error.
- [`824e835`](https://github.com/backstage/backstage/commit/824e835): Fixed `setupFilesAfterEnv` from the root `package.json` Jest configuration being shared between workspace packages, which caused each package's `src/setupTests` file to also be added to every other package.
- [`36e3f24`](https://github.com/backstage/backstage/commit/36e3f24): Fixed CommonJS frontend test execution with ESM dependencies on Node.js 24.

#### 0.1.7-next.0

##### Patch Changes

- [`36e3f24`](https://github.com/backstage/backstage/commit/36e3f24): Fixed CommonJS frontend test execution with ESM dependencies on Node.js 24.

#### 0.1.6

##### Patch Changes

- [`33c8190`](https://github.com/backstage/backstage/commit/33c8190): Made the test network request guard compatible with MSW 2 request handlers.

### `@backstage/cli-node` (0.3.4 → [0.3.6-next.0](../../changelogs/@backstage/cli-node.md#036-next0))

#### 0.3.6-next.0

##### Patch Changes

- [`4294614`](https://github.com/backstage/backstage/commit/4294614): Commands run through `runCli` now exit with the exit code they set, instead of always exiting with `0` on completion. For example, `catalog validate` and `template dry-run` now exit with a non-zero code when the input is invalid.

#### 0.3.5

##### Patch Changes

- [`3d6721d`](https://github.com/backstage/backstage/commit/3d6721d): Add intent-based CLI modules for catalog, scaffolder, and search.

  New modules provide domain-oriented subcommands that talk directly to the corresponding plugins' REST APIs:

  - `@backstage/cli-module-catalog`: `catalog list`, `catalog get`, `catalog validate`, `catalog register`, `catalog unregister`
  - `@backstage/cli-module-scaffolder`: `template list`, `template execute`, `template dry-run`
  - `@backstage/cli-module-search`: `search`, `docs search`

  The commands take their main input as a positional argument: an entity or template reference, a file path (or `-` for standard input) for `catalog validate` and `template dry-run`, a URL for `catalog register`, and the search terms for `search` and `docs search`. Repeatable `key=value` flags are used for filters, template values, and secrets, and comma-separated lists for `--fields`. Unknown flags are rejected.

  The commands that list results, `catalog list`, `template list`, `search`, and `docs search`, support `--output human` (the default) or `--output json`, along with `--limit` and `--cursor` for paging. Each command prints a single page. Human output shows how many results were shown and, when more are available, prints the `--cursor` value to continue from. All other commands always print JSON. `catalog validate` checks every entity in a multi-document YAML file and prints a JSON array with one result per entity. `catalog validate` and `template dry-run` exit with a non-zero code when the input is invalid, while connection and authentication problems are reported as errors.

  `@backstage/cli-node` now provides shared parsers for repeatable `key=value` inputs and comma-separated lists.

- [`7c6ab3d`](https://github.com/backstage/backstage/commit/7c6ab3d): Commands run through `runCli` now wait for `stdout` and `stderr` to be flushed before exiting, so large command output is no longer truncated on platforms where writes to `stdout` and `stderr` are asynchronous.
- [`6dc6bc6`](https://github.com/backstage/backstage/commit/6dc6bc6): Fixed CLIs created with `runCli` silently exiting when the root or a command group is invoked without a subcommand. They now display help for that level and complete successfully.

  Help output now lists groups and commands in separate, alphabetically sorted sections. Group previews adapt to the terminal width, using 80 columns when unavailable. Nested groups expand breadth-first when space permits; unexpanded groups retain a trailing slash and truncated previews end in an ellipsis.

#### 0.3.5-next.1

##### Patch Changes

- [`7c6ab3d`](https://github.com/backstage/backstage/commit/7c6ab3d): Commands run through `runCli` now wait for `stdout` and `stderr` to be flushed before exiting, so large command output is no longer truncated on platforms where writes to `stdout` and `stderr` are asynchronous.
- [`6dc6bc6`](https://github.com/backstage/backstage/commit/6dc6bc6): Fixed CLIs created with `runCli` silently exiting when the root or a command group is invoked without a subcommand. They now display help for that level and complete successfully.

  Help output now lists groups and commands in separate, alphabetically sorted sections. Group previews adapt to the terminal width, using 80 columns when unavailable. Nested groups expand breadth-first when space permits; unexpanded groups retain a trailing slash and truncated previews end in an ellipsis.

#### 0.3.5-next.0

##### Patch Changes

- [`3d6721d`](https://github.com/backstage/backstage/commit/3d6721d): Add intent-based CLI modules for catalog, scaffolder, and search.

  New modules provide domain-oriented subcommands that talk directly to the corresponding plugins' REST APIs:

  - `@backstage/cli-module-catalog`: `catalog list`, `catalog get`, `catalog validate`, `catalog register`, `catalog unregister`
  - `@backstage/cli-module-scaffolder`: `template list`, `template execute`, `template dry-run`
  - `@backstage/cli-module-search`: `search`, `docs search`

  The commands support human-readable and JSON output, positional entity and template references, repeatable `key=value` filters and inputs, comma-separated fields and search types, and file-based catalog entity and template input.

  `@backstage/cli-node` now provides shared parsers for repeatable `key=value` inputs and comma-separated lists.

### `@backstage/core-compat-api` (0.5.14 → [0.5.17-next.0](../../changelogs/@backstage/core-compat-api.md#0517-next0))

#### 0.5.16

##### Patch Changes

- [`8747376`](https://github.com/backstage/backstage/commit/8747376): Declared the dependencies of internally bundled code so that the package works with strict `node_modules` layouts.

### `@backstage/core-components` (0.18.13 → [0.18.16-next.0](../../changelogs/@backstage/core-components.md#01816-next0))

#### 0.18.15

##### Patch Changes

- [`e415488`](https://github.com/backstage/backstage/commit/e415488): Stop clearing the selected provider from `localStorage` when a sign-in loader is cancelled. Only clear it when the loader actually fails. Memoize `getSignInProviders` so it does not recreate the providers object on every render.
- [`76ac6ed`](https://github.com/backstage/backstage/commit/76ac6ed): Updated dependency `js-yaml` to `^5.0.0`.
- [`e859c29`](https://github.com/backstage/backstage/commit/e859c29): Added `defaultCloseDelayMs` option to `SubmenuOptions` to configure a delay before a submenu closes.

#### 0.18.15-next.3

##### Patch Changes

- [`e415488`](https://github.com/backstage/backstage/commit/e415488): Stop clearing the selected provider from `localStorage` when a sign-in loader is cancelled. Only clear it when the loader actually fails. Memoize `getSignInProviders` so it does not recreate the providers object on every render.

#### 0.18.15-next.2

##### Patch Changes

- [`76ac6ed`](https://github.com/backstage/backstage/commit/76ac6ed): Updated dependency `js-yaml` to `^5.0.0`.

#### 0.18.15-next.1

##### Patch Changes

- [`e859c29`](https://github.com/backstage/backstage/commit/e859c29): Added `defaultCloseDelayMs` option to `SubmenuOptions` to configure a delay before a submenu closes.

#### 0.18.14

##### Patch Changes

- [`b80a9f3`](https://github.com/backstage/backstage/commit/b80a9f3): Added an `onCopyLog` prop to the `LogViewer` component that renders a copy button in the toolbar, allowing users to copy all log content to the clipboard.
- [`736d84e`](https://github.com/backstage/backstage/commit/736d84e): Use locale-insensitive Unicode casing for consistent string handling across environments.
- [`a15bac8`](https://github.com/backstage/backstage/commit/a15bac8): Added an optional `variant` prop to `CopyTextButton` to allow configuring its visual style (`primary`, `secondary`, or `tertiary`).
- [`c0ebaa7`](https://github.com/backstage/backstage/commit/c0ebaa7): chore(deps): bump `js-yaml` from 4.3.1 to 4.3.2
- [`bfb6497`](https://github.com/backstage/backstage/commit/bfb6497): Fixed `CopyTextButton` showing its tooltip on hover/focus instead of only after the user clicks to copy the text.
- [`279fdf6`](https://github.com/backstage/backstage/commit/279fdf6): Declared the DOM Testing Library dependency required by React Testing Library.
- [`f2b5407`](https://github.com/backstage/backstage/commit/f2b5407): Updated dependency `react-idle-timer` to `5.7.3`.
- [`d9a949e`](https://github.com/backstage/backstage/commit/d9a949e): Added support for rendering custom link elements inside `HeaderIconLinkRow`.

#### 0.18.14-next.1

##### Patch Changes

- [`b80a9f3`](https://github.com/backstage/backstage/commit/b80a9f3): Added an `onCopyLog` prop to the `LogViewer` component that renders a copy button in the toolbar, allowing users to copy all log content to the clipboard.
- [`279fdf6`](https://github.com/backstage/backstage/commit/279fdf6): Declared the DOM Testing Library dependency required by React Testing Library.

### `@backstage/create-app` (0.9.1 → [0.9.4-next.0](../../changelogs/@backstage/create-app.md#094-next0))

#### 0.9.4-next.0

##### Patch Changes

- [`77f9227`](https://github.com/backstage/backstage/commit/77f9227): New apps now declare support for light and dark color schemes and apply the stored theme choice before the app loads. The browser's default page background, scrollbars and form controls then match the theme during loading, instead of always starting out light. A new `public/theme.js` applies a stored light or dark choice, and the OS preference is used otherwise.

  To add this to an existing app, copy `packages/app/public/theme.js` from a newly created app, and add `<meta name="color-scheme" content="light dark" />` and `<script src="<%= publicPath %>/theme.js"></script>` to the `<head>` of `packages/app/public/index.html`.

#### 0.9.3

##### Patch Changes

- [`2e0776c`](https://github.com/backstage/backstage/commit/2e0776c): Bumped create-app version.
- [`d4ef6c6`](https://github.com/backstage/backstage/commit/d4ef6c6): Bumped create-app version.
- [`fc94744`](https://github.com/backstage/backstage/commit/fc94744): Fixed default landing page configuration in the app template so the Home page path override is inside the existing `page:home` block.
- [`36e3f24`](https://github.com/backstage/backstage/commit/36e3f24): Updated generated applications to use the latest Jest 30 release.
- [`bf3db11`](https://github.com/backstage/backstage/commit/bf3db11): Pinned Yarn core in newly generated apps to avoid installation failures from a broken upstream release.

#### 0.9.3-next.3

##### Patch Changes

- Bumped create-app version.

#### 0.9.3-next.2

##### Patch Changes

- Bumped create-app version.

#### 0.9.3-next.1

##### Patch Changes

- [`bf3db11`](https://github.com/backstage/backstage/commit/bf3db11): Pinned Yarn core in newly generated apps to avoid installation failures from a broken upstream release.

#### 0.9.3-next.0

##### Patch Changes

- [`36e3f24`](https://github.com/backstage/backstage/commit/36e3f24): Updated generated applications to use the latest Jest 30 release.

#### 0.9.2

##### Patch Changes

- [`736d84e`](https://github.com/backstage/backstage/commit/736d84e): Use locale-insensitive Unicode casing for consistent string handling across environments.
- [`1a8a90c`](https://github.com/backstage/backstage/commit/1a8a90c): Bumped create-app version.
- [`6eec9b5`](https://github.com/backstage/backstage/commit/6eec9b5): Bumped create-app version.
- [`c3150c3`](https://github.com/backstage/backstage/commit/c3150c3): Bumped create-app version.

#### 0.9.2-next.2

##### Patch Changes

- Bumped create-app version.

#### 0.9.2-next.1

##### Patch Changes

- Bumped create-app version.

#### 0.9.2-next.0

##### Patch Changes

- Bumped create-app version.

### `@backstage/eslint-plugin` (0.3.2 → [0.3.4-next.0](../../changelogs/@backstage/eslint-plugin.md#034-next0))

#### 0.3.4-next.0

##### Patch Changes

- [`245d9e3`](https://github.com/backstage/backstage/commit/245d9e3): Internal changes for TypeScript 7 compatibility. The rules work the same as before.

#### 0.3.3

##### Patch Changes

- [`914101d`](https://github.com/backstage/backstage/commit/914101d): The `no-mixed-plugin-imports` rule now also applies when the repository is checked out below a directory whose name starts with a dot, such as `~/.worktrees/my-repo`. Before, it silently reported nothing in such locations, because `includedFiles` was matched only against the absolute file path. Patterns are now matched against the path relative to the package directory as well.

### `@backstage/frontend-app-api` (0.16.7 → [0.16.10-next.0](../../changelogs/@backstage/frontend-app-api.md#01610-next0))

#### 0.16.9

##### Patch Changes

- [`0caa896`](https://github.com/backstage/backstage/commit/0caa896): Provided an implementation of `AppLifecycleApi` and updated the app preparation and finalization process to utilize this API.
- [`5b67e11`](https://github.com/backstage/backstage/commit/5b67e11): The permission check for extension `if` predicates during app startup now retries network failures and 5xx responses, for up to about 15 seconds, instead of failing the whole app on the first error. This helps when the frontend comes up before the permission backend, and when a request is dropped during sign-in.
- [`d810cc9`](https://github.com/backstage/backstage/commit/d810cc9): Improved link resolution performance by reusing route matches for recently visited locations.

#### 0.16.9-next.1

##### Patch Changes

- [`0caa896`](https://github.com/backstage/backstage/commit/0caa896): Provided an implementation of `AppLifecycleApi` and updated the app preparation and finalization process to utilize this API.
- [`d810cc9`](https://github.com/backstage/backstage/commit/d810cc9): Improved link resolution performance by reusing route matches for recently visited locations.

#### 0.16.8

##### Patch Changes

- [`52022b9`](https://github.com/backstage/backstage/commit/52022b9): Fixed `app.extensions` shorthand and `disabled` field to accept boolean-ish strings (`'true'`/`'false'`), so environment variable substitution can be used to toggle extensions, e.g. `${CATALOG_OVERVIEW_ENABLED}`.

#### 0.16.8-next.1

##### Patch Changes

- [`52022b9`](https://github.com/backstage/backstage/commit/52022b9): Fixed `app.extensions` shorthand and `disabled` field to accept boolean-ish strings (`'true'`/`'false'`), so environment variable substitution can be used to toggle extensions, e.g. `${CATALOG_OVERVIEW_ENABLED}`.

### `@backstage/frontend-dynamic-feature-loader` (0.1.15 → [0.1.18-next.0](../../changelogs/@backstage/frontend-dynamic-feature-loader.md#0118-next0))

#### 0.1.16

##### Patch Changes

- [`064c2de`](https://github.com/backstage/backstage/commit/064c2de): Updated the Module Federation dependencies to versions that avoid known security vulnerabilities.

#### 0.1.16-next.1

##### Patch Changes

- [`064c2de`](https://github.com/backstage/backstage/commit/064c2de): Updated the Module Federation dependencies to versions that avoid known security vulnerabilities.

### `@backstage/frontend-plugin-api` (0.18.0 → [0.18.3-next.0](../../changelogs/@backstage/frontend-plugin-api.md#0183-next0))

#### 0.18.3-next.0

##### Patch Changes

- [`ac2de0f`](https://github.com/backstage/backstage/commit/ac2de0f): Fixed a "Type instantiation is excessively deep and possibly infinite" error from `createFrontendPlugin` in plugins with many extensions, in particular with TypeScript 5.9 and later. In rare cases, the extensions in the type of a plugin may be in a different order or include extensions that were missing before.
- [`8ca78a2`](https://github.com/backstage/backstage/commit/8ca78a2): Added `coreApis`, a namespace of core Utility API refs. The deprecated Alert API is excluded in favor of Toast. The individual refs with namespace equivalents are deprecated in favor of their `coreApis` equivalents, while remaining compatible. Provider-specific authentication refs remain separate and are not deprecated.

#### 0.18.2

##### Patch Changes

- [`a650c4f`](https://github.com/backstage/backstage/commit/a650c4f): Added `AppLifecycleApi` and `appLifecycleApiRef`, which let you check whether the app has been finalized and subscribe to changes in its lifecycle.
- [`a650c4f`](https://github.com/backstage/backstage/commit/a650c4f): The `useRouteRef` hook now resolves the route again once the app has been finalized, so that elements rendered before finalization, such as `app/root.elements` extensions, can link to pages instead of getting `undefined`.

#### 0.18.2-next.1

##### Patch Changes

- [`a650c4f`](https://github.com/backstage/backstage/commit/a650c4f): Added `AppLifecycleApi` and `appLifecycleApiRef`, which let you check whether the app has been finalized and subscribe to changes in its lifecycle.
- [`a650c4f`](https://github.com/backstage/backstage/commit/a650c4f): The `useRouteRef` hook now resolves the route again once the app has been finalized, so that elements rendered before finalization, such as `app/root.elements` extensions, can link to pages instead of getting `undefined`.

#### 0.18.1

##### Patch Changes

- [`024c0ef`](https://github.com/backstage/backstage/commit/024c0ef): Updated internal type imports to avoid circular declaration chunks in package builds.
- [`bd6cf43`](https://github.com/backstage/backstage/commit/bd6cf43): Fixed a bug where overriding a plugin extension with `withOverrides` moved the overridden extension to the end of the plugin's extension list. This caused overridden extensions to lose their original position, for example making an overridden sub page tab move to the end of the tabs on its page. Overridden extensions now keep their original order, while extensions that don't override an existing one are appended at the end.

#### 0.18.1-next.0

##### Patch Changes

- [`024c0ef`](https://github.com/backstage/backstage/commit/024c0ef): Updated internal type imports to avoid circular declaration chunks in package builds.

### `@backstage/module-federation-common` (0.1.4 → [0.1.6](../../changelogs/@backstage/module-federation-common.md#016))

#### 0.1.5

##### Patch Changes

- [`064c2de`](https://github.com/backstage/backstage/commit/064c2de): Updated the Module Federation dependencies to versions that avoid known security vulnerabilities.

### `@backstage/plugin-api-docs` (0.14.4 → [0.14.7-next.0](../../changelogs/@backstage/plugin-api-docs.md#0147-next0))

#### 0.14.5

##### Patch Changes

- [`736d84e`](https://github.com/backstage/backstage/commit/736d84e): Use locale-insensitive Unicode casing for consistent string handling across environments.
- [`4b643e3`](https://github.com/backstage/backstage/commit/4b643e3): Migrate plugin-api-docs to the configSchema API to remove the deprecated config.schema usage.

### `@backstage/plugin-app` (0.5.2 → [0.5.5-next.0](../../changelogs/@backstage/plugin-app.md#055-next0))

#### 0.5.4

##### Patch Changes

- [`4e7a710`](https://github.com/backstage/backstage/commit/4e7a710): Updated React Aria dependencies to the October 2026 release.
- [`8747376`](https://github.com/backstage/backstage/commit/8747376): Declared the dependencies of internally bundled code so that the package works with strict `node_modules` layouts, and stopped loading the default API implementations just to install the default icons.
- [`1eeab07`](https://github.com/backstage/backstage/commit/1eeab07): Fixed long words in toast titles and descriptions overflowing the notification and overlapping the close button.

#### 0.5.4-next.1

##### Patch Changes

- [`4e7a710`](https://github.com/backstage/backstage/commit/4e7a710): Updated React Aria dependencies to the October 2026 release.
- [`1eeab07`](https://github.com/backstage/backstage/commit/1eeab07): Fixed long words in toast titles and descriptions overflowing the notification and overlapping the close button.

#### 0.5.3

##### Patch Changes

- [`d421187`](https://github.com/backstage/backstage/commit/d421187): Reduced the initial app bundle size by loading page and optional UI implementations only when their extensions render.
- [`f914343`](https://github.com/backstage/backstage/commit/f914343): Fixed toast text layout when the application does not define a global line height.

#### 0.5.3-next.1

##### Patch Changes

- [`d421187`](https://github.com/backstage/backstage/commit/d421187): Reduced the initial app bundle size by loading page and optional UI implementations only when their extensions render.

#### 0.5.3-next.0

##### Patch Changes

- [`f914343`](https://github.com/backstage/backstage/commit/f914343): Fixed toast text layout when the application does not define a global line height.

### `@backstage/plugin-app-backend` (0.5.17 → [0.5.20-next.0](../../changelogs/@backstage/plugin-app-backend.md#0520-next0))

#### 0.5.20-next.0

##### Patch Changes

- [`11f4455`](https://github.com/backstage/backstage/commit/11f4455): Documented that if your package manager doesn't hoist workspace packages, for example pnpm with `hoistWorkspacePackages: false`, you need to add the app package to the `dependencies` of the root `package.json`.
- [`2fea3e2`](https://github.com/backstage/backstage/commit/2fea3e2): Reduced startup database traffic and memory usage when checking for previously cached static assets.

#### 0.5.19

##### Patch Changes

- [`a18df8f`](https://github.com/backstage/backstage/commit/a18df8f): Added optional `app.publicConfig` allowlists for config key paths and extension IDs exposed to unauthenticated users of protected apps. Authenticated users retain access to all frontend-visible configuration, and existing behavior is unchanged unless filtering is enabled.
- [`c55505e`](https://github.com/backstage/backstage/commit/c55505e): Fix protected app sign-in returning a 404 when an authenticated browser repeats the sign-in handoff for the same user.

#### 0.5.19-next.2

##### Patch Changes

- [`c55505e`](https://github.com/backstage/backstage/commit/c55505e): Fix protected app sign-in returning a 404 when an authenticated browser repeats the sign-in handoff for the same user.

### `@backstage/plugin-app-module-user-settings` (0.1.1 → [0.1.4-next.0](../../changelogs/@backstage/plugin-app-module-user-settings.md#014-next0))

#### 0.1.2

##### Patch Changes

- [`4cba335`](https://github.com/backstage/backstage/commit/4cba335): Fixes published entry point configurations so it can be imported reliably in Jest/Node resolution.

#### 0.1.2-next.0

##### Patch Changes

- [`4cba335`](https://github.com/backstage/backstage/commit/4cba335): Fixes published entry point configurations so it can be imported reliably in Jest/Node resolution.

### `@backstage/plugin-app-react` (0.2.6 → [0.2.9-next.0](../../changelogs/@backstage/plugin-app-react.md#029-next0))

#### 0.2.7

##### Patch Changes

- [`40838dc`](https://github.com/backstage/backstage/commit/40838dc): Added an extension boundary around custom navigation content.

#### 0.2.7-next.1

##### Patch Changes

- [`40838dc`](https://github.com/backstage/backstage/commit/40838dc): Added an extension boundary around custom navigation content.

### `@backstage/plugin-app-visualizer` (0.2.7 → [0.2.10-next.0](../../changelogs/@backstage/plugin-app-visualizer.md#0210-next0))

#### 0.2.9

##### Patch Changes

- [`4e7a710`](https://github.com/backstage/backstage/commit/4e7a710): Updated React Aria dependencies to the October 2026 release.
- [`13adaa1`](https://github.com/backstage/backstage/commit/13adaa1): Updated internal React component names to improve debugging and tooling compatibility.

#### 0.2.9-next.2

##### Patch Changes

- [`4e7a710`](https://github.com/backstage/backstage/commit/4e7a710): Updated React Aria dependencies to the October 2026 release.

#### 0.2.9-next.1

##### Patch Changes

- [`13adaa1`](https://github.com/backstage/backstage/commit/13adaa1): Updated internal React component names to improve debugging and tooling compatibility.

### `@backstage/plugin-auth-backend` (0.30.0 → [0.30.3-next.0](../../changelogs/@backstage/plugin-auth-backend.md#0303-next0))

#### 0.30.3-next.0

##### Patch Changes

- [`8965c27`](https://github.com/backstage/backstage/commit/8965c27): User tokens issued by sign-in resolvers now always have the entity refs in their `sub` and `ent` claims in canonical form, for example `user:default/jane.doe` rather than `User:default/Jane.Doe`, and duplicate `ent` refs are removed. Previously, a custom sign-in resolver could issue valid but non-canonical refs, which then failed to match stored user info and offline sessions on case-sensitive databases.
- [`fa0eb7a`](https://github.com/backstage/backstage/commit/fa0eb7a): Added a `POST /v1/offline-sessions/revoke` endpoint that lets other backend services revoke all offline sessions (refresh tokens) of a user. The endpoint only accepts service credentials, records an audit event, and is only available when `auth.experimentalRefreshToken.enabled` is set.
- [`918ca98`](https://github.com/backstage/backstage/commit/918ca98): Updated dependency `jose` to `^6.1.0`. Existing ES256 token issuance and verification are unchanged. ML-DSA algorithms can be used when the runtime supports them.

#### 0.30.1

##### Patch Changes

- [`736d84e`](https://github.com/backstage/backstage/commit/736d84e): Use locale-insensitive Unicode casing for consistent string handling across environments.
- [`08c5d9b`](https://github.com/backstage/backstage/commit/08c5d9b): Fixed inconsistent URL pattern matching in token revocation.

#### 0.30.1-next.0

##### Patch Changes

- [`08c5d9b`](https://github.com/backstage/backstage/commit/08c5d9b): Fixed inconsistent URL pattern matching in token revocation.

### `@backstage/plugin-auth-backend-module-auth0-provider` (0.4.4 → [0.4.7-next.0](../../changelogs/@backstage/plugin-auth-backend-module-auth0-provider.md#047-next0))

#### 0.4.7-next.0

##### Patch Changes

- [`918ca98`](https://github.com/backstage/backstage/commit/918ca98): Updated dependency `jose` to `^6.1.0`. Existing ES256 token issuance and verification are unchanged. ML-DSA algorithms can be used when the runtime supports them.

### `@backstage/plugin-auth-backend-module-aws-alb-provider` (0.4.19 → [0.4.22-next.0](../../changelogs/@backstage/plugin-auth-backend-module-aws-alb-provider.md#0422-next0))

#### 0.4.22-next.0

##### Patch Changes

- [`918ca98`](https://github.com/backstage/backstage/commit/918ca98): Updated dependency `jose` to `^6.1.0`. Existing ES256 token issuance and verification are unchanged. ML-DSA algorithms can be used when the runtime supports them.

### `@backstage/plugin-auth-backend-module-azure-easyauth-provider` (0.2.23 → [0.2.26-next.0](../../changelogs/@backstage/plugin-auth-backend-module-azure-easyauth-provider.md#0226-next0))

#### 0.2.26-next.0

##### Patch Changes

- [`918ca98`](https://github.com/backstage/backstage/commit/918ca98): Updated dependency `jose` to `^6.1.0`. Existing ES256 token issuance and verification are unchanged. ML-DSA algorithms can be used when the runtime supports them.

#### 0.2.24

##### Patch Changes

- [`736d84e`](https://github.com/backstage/backstage/commit/736d84e): Use locale-insensitive Unicode casing for consistent string handling across environments.

### `@backstage/plugin-auth-backend-module-gcp-iap-provider` (0.4.18 → [0.4.21-next.0](../../changelogs/@backstage/plugin-auth-backend-module-gcp-iap-provider.md#0421-next0))

#### 0.4.20

##### Patch Changes

- [`b96ec9e`](https://github.com/backstage/backstage/commit/b96ec9e): Cache Google IAP public verification keys according to the response cache headers to reduce repeated key requests during authentication.

#### 0.4.20-next.0

##### Patch Changes

- [`b96ec9e`](https://github.com/backstage/backstage/commit/b96ec9e): Cache Google IAP public verification keys according to the response cache headers to reduce repeated key requests during authentication.

### `@backstage/plugin-auth-backend-module-github-provider` (0.5.6 → [0.5.9-next.0](../../changelogs/@backstage/plugin-auth-backend-module-github-provider.md#059-next0))

#### 0.5.7

##### Patch Changes

- [`211a61a`](https://github.com/backstage/backstage/commit/211a61a): Deprecated the GitHub username sign-in resolver in favor of the stable user ID resolver. GitHub user ID catalog lookups now require an exact match and handle candidates that differ only by letter casing.

### `@backstage/plugin-auth-backend-module-guest-provider` (0.2.22 → [0.2.25-next.0](../../changelogs/@backstage/plugin-auth-backend-module-guest-provider.md#0225-next0))

#### 0.2.24

##### Patch Changes

- [`c2ea521`](https://github.com/backstage/backstage/commit/c2ea521): Change visibility to auth.providers.guest configuration key to be visible by frontend plugins to align with other authentication providers.

#### 0.2.24-next.0

##### Patch Changes

- [`c2ea521`](https://github.com/backstage/backstage/commit/c2ea521): Change visibility to auth.providers.guest configuration key to be visible by frontend plugins to align with other authentication providers.

### `@backstage/plugin-auth-backend-module-microsoft-provider` (0.3.18 → [0.3.21-next.0](../../changelogs/@backstage/plugin-auth-backend-module-microsoft-provider.md#0321-next0))

#### 0.3.21-next.0

##### Patch Changes

- [`918ca98`](https://github.com/backstage/backstage/commit/918ca98): Updated dependency `jose` to `^6.1.0`. Existing ES256 token issuance and verification are unchanged. ML-DSA algorithms can be used when the runtime supports them.

#### 0.3.19

##### Patch Changes

- [`736d84e`](https://github.com/backstage/backstage/commit/736d84e): Use locale-insensitive Unicode casing for consistent string handling across environments.

### `@backstage/plugin-auth-backend-module-oauth2-proxy-provider` (0.3.2 → [0.3.5-next.0](../../changelogs/@backstage/plugin-auth-backend-module-oauth2-proxy-provider.md#035-next0))

#### 0.3.5-next.0

##### Patch Changes

- [`918ca98`](https://github.com/backstage/backstage/commit/918ca98): Updated dependency `jose` to `^6.1.0`. Existing ES256 token issuance and verification are unchanged. ML-DSA algorithms can be used when the runtime supports them.

#### 0.3.3

##### Patch Changes

- [`736d84e`](https://github.com/backstage/backstage/commit/736d84e): Use locale-insensitive Unicode casing for consistent string handling across environments.

### `@backstage/plugin-auth-backend-module-oidc-provider` (0.4.20 → [0.4.23-next.0](../../changelogs/@backstage/plugin-auth-backend-module-oidc-provider.md#0423-next0))

#### 0.4.23-next.0

##### Patch Changes

- [`918ca98`](https://github.com/backstage/backstage/commit/918ca98): Updated dependency `jose` to `^6.1.0`. Existing ES256 token issuance and verification are unchanged. ML-DSA algorithms can be used when the runtime supports them.

#### 0.4.21

##### Patch Changes

- [`a818233`](https://github.com/backstage/backstage/commit/a818233): Omit email addresses from the default OIDC profile unless the identity provider marks them as verified.

#### 0.4.21-next.1

##### Patch Changes

- [`a818233`](https://github.com/backstage/backstage/commit/a818233): Omit email addresses from the default OIDC profile unless the identity provider marks them as verified.

### `@backstage/plugin-auth-backend-module-pinniped-provider` (0.3.17 → [0.3.20-next.0](../../changelogs/@backstage/plugin-auth-backend-module-pinniped-provider.md#0320-next0))

#### 0.3.20-next.0

##### Patch Changes

- [`918ca98`](https://github.com/backstage/backstage/commit/918ca98): Updated dependency `jose` to `^6.1.0`. Existing ES256 token issuance and verification are unchanged. ML-DSA algorithms can be used when the runtime supports them.

#### 0.3.18

##### Patch Changes

- [`623e9d4`](https://github.com/backstage/backstage/commit/623e9d4): Prevented an unavailable Pinniped supervisor during provider startup from causing an unhandled promise rejection before the first authentication request.

### `@backstage/plugin-auth-backend-module-vmware-cloud-provider` (0.5.17 → [0.5.20-next.0](../../changelogs/@backstage/plugin-auth-backend-module-vmware-cloud-provider.md#0520-next0))

#### 0.5.20-next.0

##### Patch Changes

- [`918ca98`](https://github.com/backstage/backstage/commit/918ca98): Updated dependency `jose` to `^6.1.0`. Existing ES256 token issuance and verification are unchanged. ML-DSA algorithms can be used when the runtime supports them.

### `@backstage/plugin-auth-node` (0.7.5 → [0.7.8-next.0](../../changelogs/@backstage/plugin-auth-node.md#078-next0))

#### 0.7.8-next.0

##### Patch Changes

- [`918ca98`](https://github.com/backstage/backstage/commit/918ca98): Updated dependency `jose` to `^6.1.0`. Existing ES256 token issuance and verification are unchanged. ML-DSA algorithms can be used when the runtime supports them.

#### 0.7.7

##### Patch Changes

- [`9724edd`](https://github.com/backstage/backstage/commit/9724edd): Hardened return URL validation in the OAuth redirect flow. Failed sign-in attempts now return to the configured app URL with the error message, including when the return URL is invalid.

#### 0.7.6

##### Patch Changes

- [`507e65a`](https://github.com/backstage/backstage/commit/507e65a): OAuth profile normalization now respects matching negative email verification information supplied by the provider.

### `@backstage/plugin-bitbucket-cloud-common` (0.3.12 → [0.3.14](../../changelogs/@backstage/plugin-bitbucket-cloud-common.md#0314))

#### 0.3.14

##### Patch Changes

- [`0c9d72c`](https://github.com/backstage/backstage/commit/0c9d72c): Update Bitbucket Cloud Authentication logic to support bearer API token

#### 0.3.13

##### Patch Changes

- [`0c1b8ee`](https://github.com/backstage/backstage/commit/0c1b8ee): Updated the OpenAPI generator tooling to avoid known security vulnerabilities.

### `@backstage/plugin-catalog-backend-module-aws` (0.4.27 → [0.4.30-next.0](../../changelogs/@backstage/plugin-catalog-backend-module-aws.md#0430-next0))

#### 0.4.28

##### Patch Changes

- [`8b3c83e`](https://github.com/backstage/backstage/commit/8b3c83e): Improved handling of AWS S3 object keys when creating catalog locations.
- [`736d84e`](https://github.com/backstage/backstage/commit/736d84e): Use locale-insensitive Unicode casing for consistent string handling across environments.

#### 0.4.28-next.1

##### Patch Changes

- [`8b3c83e`](https://github.com/backstage/backstage/commit/8b3c83e): Improved handling of AWS S3 object keys when creating catalog locations.

### `@backstage/plugin-catalog-backend-module-azure` (0.3.21 → [0.3.24-next.0](../../changelogs/@backstage/plugin-catalog-backend-module-azure.md#0324-next0))

#### 0.3.22

##### Patch Changes

- [`8b3c83e`](https://github.com/backstage/backstage/commit/8b3c83e): Improved handling of Azure Blob Storage blob names when creating catalog locations.

#### 0.3.22-next.0

##### Patch Changes

- [`8b3c83e`](https://github.com/backstage/backstage/commit/8b3c83e): Improved handling of Azure Blob Storage blob names when creating catalog locations.

### `@backstage/plugin-catalog-backend-module-bitbucket-server` (0.5.14 → [0.5.17-next.0](../../changelogs/@backstage/plugin-catalog-backend-module-bitbucket-server.md#0517-next0))

#### 0.5.15

##### Patch Changes

- [`989db63`](https://github.com/backstage/backstage/commit/989db63): Aligned event-driven catalog updates with the repository filters configured for the Bitbucket Server provider.

### `@backstage/plugin-catalog-backend-module-gitea` (0.1.15 → [0.1.18-next.0](../../changelogs/@backstage/plugin-catalog-backend-module-gitea.md#0118-next0))

#### 0.1.17

##### Patch Changes

- [`f181c5f`](https://github.com/backstage/backstage/commit/f181c5f): Fixed the Gitea entity provider registering catalog-info.yaml locations against a hardcoded 'main' branch instead of each repository's actual default branch.

#### 0.1.17-next.2

##### Patch Changes

- [`f181c5f`](https://github.com/backstage/backstage/commit/f181c5f): Fixed the Gitea entity provider registering catalog-info.yaml locations against a hardcoded 'main' branch instead of each repository's actual default branch.

### `@backstage/plugin-catalog-backend-module-gitlab` (0.8.7 → [0.8.10-next.0](../../changelogs/@backstage/plugin-catalog-backend-module-gitlab.md#0810-next0))

#### 0.8.10-next.0

##### Patch Changes

- [`ca14116`](https://github.com/backstage/backstage/commit/ca14116): Moved `@gitbeaker/rest` to dev dependencies, since it is only used for types.

#### 0.8.8

##### Patch Changes

- [`348bea1`](https://github.com/backstage/backstage/commit/348bea1): Fixed `GitlabDiscoveryEntityProvider` to only process push events targeting the configured branch.
- [`b7db066`](https://github.com/backstage/backstage/commit/b7db066): Fixed a scope validation issue in GitLab organization discovery.

#### 0.8.8-next.1

##### Patch Changes

- [`b7db066`](https://github.com/backstage/backstage/commit/b7db066): Fixed a scope validation issue in GitLab organization discovery.

### `@backstage/plugin-catalog-backend-module-ldap` (0.12.8 → [0.12.11-next.0](../../changelogs/@backstage/plugin-catalog-backend-module-ldap.md#01211-next0))

#### 0.12.10

##### Patch Changes

- [`916e5b2`](https://github.com/backstage/backstage/commit/916e5b2): Improved the performance of LDAP organization ingestion, especially for large directories, without changing the resulting catalog entities.
- [`1a20364`](https://github.com/backstage/backstage/commit/1a20364): Improved large LDAP organization refreshes by yielding to the event loop while resolving relations.

#### 0.12.10-next.0

##### Patch Changes

- [`916e5b2`](https://github.com/backstage/backstage/commit/916e5b2): Improved the performance of LDAP organization ingestion, especially for large directories, without changing the resulting catalog entities.
- [`1a20364`](https://github.com/backstage/backstage/commit/1a20364): Improved large LDAP organization refreshes by yielding to the event loop while resolving relations.

#### 0.12.9

##### Patch Changes

- [`736d84e`](https://github.com/backstage/backstage/commit/736d84e): Use locale-insensitive Unicode casing for consistent string handling across environments.

### `@backstage/plugin-catalog-backend-module-msgraph` (0.10.5 → [0.10.8-next.0](../../changelogs/@backstage/plugin-catalog-backend-module-msgraph.md#0108-next0))

#### 0.10.6

##### Patch Changes

- [`736d84e`](https://github.com/backstage/backstage/commit/736d84e): Use locale-insensitive Unicode casing for consistent string handling across environments.
- [`7ac10da`](https://github.com/backstage/backstage/commit/7ac10da): Fixed accumulating abort listeners on `MicrosoftGraphClient`.

#### 0.10.6-next.0

##### Patch Changes

- [`7ac10da`](https://github.com/backstage/backstage/commit/7ac10da): Fixed accumulating abort listeners on `MicrosoftGraphClient`.

### `@backstage/plugin-catalog-backend-module-puppetdb` (0.2.25 → [0.2.28-next.0](../../changelogs/@backstage/plugin-catalog-backend-module-puppetdb.md#0228-next0))

#### 0.2.26

##### Patch Changes

- [`736d84e`](https://github.com/backstage/backstage/commit/736d84e): Use locale-insensitive Unicode casing for consistent string handling across environments.

### `@backstage/plugin-catalog-backend-module-unprocessed` (0.6.15 → [0.6.18-next.0](../../changelogs/@backstage/plugin-catalog-backend-module-unprocessed.md#0618-next0))

#### 0.6.18-next.0

##### Patch Changes

- [`af39b90`](https://github.com/backstage/backstage/commit/af39b90): Fixed pending entities being returned without their entity ID and entity ref.

### `@backstage/plugin-catalog-graph` (0.6.7 → [0.6.10-next.0](../../changelogs/@backstage/plugin-catalog-graph.md#0610-next0))

#### 0.6.9

##### Patch Changes

- [`cc7eccf`](https://github.com/backstage/backstage/commit/cc7eccf): The catalog graph page in the new frontend system no longer renders its own legacy header, and instead uses the page header provided by the app. Apps that use the old frontend system are not affected.

#### 0.6.8

##### Patch Changes

- [`736d84e`](https://github.com/backstage/backstage/commit/736d84e): Use locale-insensitive Unicode casing for consistent string handling across environments.

### `@backstage/plugin-catalog-import` (0.13.17 → [0.13.20-next.0](../../changelogs/@backstage/plugin-catalog-import.md#01320-next0))

#### 0.13.19

##### Patch Changes

- [`3a0ac14`](https://github.com/backstage/backstage/commit/3a0ac14): The catalog import page in the new frontend system no longer renders its own legacy header, and instead uses the page header provided by the app. Apps that use the old frontend system are not affected.

#### 0.13.18

##### Patch Changes

- [`736d84e`](https://github.com/backstage/backstage/commit/736d84e): Use locale-insensitive Unicode casing for consistent string handling across environments.
- [`5d6a62b`](https://github.com/backstage/backstage/commit/5d6a62b): Fixed the owner selected in the import stepper being written to the generated `catalog-info.yaml` as a display name instead of an entity reference. Groups are still suggested by their display name, but selecting one now sets a valid `spec.owner`, for example picking `My Team` results in `my-team`.
- [`d421187`](https://github.com/backstage/backstage/commit/d421187): Reduced the initial app bundle size by loading page and optional UI implementations only when their extensions render.

#### 0.13.18-next.1

##### Patch Changes

- [`d421187`](https://github.com/backstage/backstage/commit/d421187): Reduced the initial app bundle size by loading page and optional UI implementations only when their extensions render.

### `@backstage/plugin-catalog-unprocessed-entities` (0.2.34 → [0.2.37-next.0](../../changelogs/@backstage/plugin-catalog-unprocessed-entities.md#0237-next0))

#### 0.2.35

##### Patch Changes

- [`736d84e`](https://github.com/backstage/backstage/commit/736d84e): Use locale-insensitive Unicode casing for consistent string handling across environments.
- [`d421187`](https://github.com/backstage/backstage/commit/d421187): Reduced the initial app bundle size by loading page and optional UI implementations only when their extensions render.

#### 0.2.35-next.1

##### Patch Changes

- [`d421187`](https://github.com/backstage/backstage/commit/d421187): Reduced the initial app bundle size by loading page and optional UI implementations only when their extensions render.

### `@backstage/plugin-devtools` (0.1.42 → [0.1.45-next.0](../../changelogs/@backstage/plugin-devtools.md#0145-next0))

#### 0.1.44

##### Patch Changes

- [`cde2e67`](https://github.com/backstage/backstage/commit/cde2e67): Migrated `InfoContent` component from Material UI to Backstage UI (BUI).

#### 0.1.43

##### Patch Changes

- [`d421187`](https://github.com/backstage/backstage/commit/d421187): Reduced the initial app bundle size by loading page and optional UI implementations only when their extensions render.
- [`38441ff`](https://github.com/backstage/backstage/commit/38441ff): Migrate to toastApi from deprecated alertApi

#### 0.1.43-next.2

##### Patch Changes

- [`38441ff`](https://github.com/backstage/backstage/commit/38441ff): Migrate to toastApi from deprecated alertApi

#### 0.1.43-next.1

##### Patch Changes

- [`d421187`](https://github.com/backstage/backstage/commit/d421187): Reduced the initial app bundle size by loading page and optional UI implementations only when their extensions render.

### `@backstage/plugin-events-backend` (0.6.5 → [0.6.8-next.0](../../changelogs/@backstage/plugin-events-backend.md#068-next0))

#### 0.6.8-next.0

##### Patch Changes

- [`a1ca033`](https://github.com/backstage/backstage/commit/a1ca033): Fixed the database event bus listener connection inheriting the trace context of the request that first opened it. Its keepalive queries are now recorded as separate root spans instead of being attached to that request's trace for as long as the connection stays open.

#### 0.6.7

##### Patch Changes

- [`02fd3bf`](https://github.com/backstage/backstage/commit/02fd3bf): Improve database event cleanup under large backlogs and speed up reading events for subscriptions with many retained events.

#### 0.6.7-next.2

##### Patch Changes

- [`02fd3bf`](https://github.com/backstage/backstage/commit/02fd3bf): Improve database event cleanup under large backlogs and speed up reading events for subscriptions with many retained events.

### `@backstage/plugin-home` (0.9.9 → [0.9.12-next.0](../../changelogs/@backstage/plugin-home.md#0912-next0))

#### 0.9.10

##### Patch Changes

- [`736d84e`](https://github.com/backstage/backstage/commit/736d84e): Use locale-insensitive Unicode casing for consistent string handling across environments.
- [`d421187`](https://github.com/backstage/backstage/commit/d421187): Reduced the initial app bundle size by loading page and optional UI implementations only when their extensions render.
- [`bca8281`](https://github.com/backstage/backstage/commit/bca8281): Fix clock configuration handling and use lazy initialization for the clocks state.

#### 0.9.10-next.1

##### Patch Changes

- [`d421187`](https://github.com/backstage/backstage/commit/d421187): Reduced the initial app bundle size by loading page and optional UI implementations only when their extensions render.

### `@backstage/plugin-home-react` (0.1.41 → [0.1.44-next.0](../../changelogs/@backstage/plugin-home-react.md#0144-next0))

#### 0.1.42

##### Patch Changes

- [`cd4a9c7`](https://github.com/backstage/backstage/commit/cd4a9c7): Fixed `CardExtension` to avoid requiring app context when a custom `Renderer` is provided.

### `@backstage/plugin-kubernetes` (0.12.22 → [0.12.25-next.0](../../changelogs/@backstage/plugin-kubernetes.md#01225-next0))

#### 0.12.23

##### Patch Changes

- [`83f34f2`](https://github.com/backstage/backstage/commit/83f34f2): The Kubernetes entity content no longer loads its UI until the tab is opened, keeping it out of the initial bundle. Tab visibility is now an entity filter predicate that can be overridden through app config, and entities with an empty Kubernetes annotation now show the tab where previously it was hidden.

#### 0.12.23-next.1

##### Patch Changes

- [`83f34f2`](https://github.com/backstage/backstage/commit/83f34f2): The Kubernetes entity content no longer loads its UI until the tab is opened, keeping it out of the initial bundle. Tab visibility is now an entity filter predicate that can be overridden through app config, and entities with an empty Kubernetes annotation now show the tab where previously it was hidden.

### `@backstage/plugin-kubernetes-backend` (0.21.10 → [0.21.13-next.0](../../changelogs/@backstage/plugin-kubernetes-backend.md#02113-next0))

#### 0.21.12

##### Patch Changes

- [`66f8cf8`](https://github.com/backstage/backstage/commit/66f8cf8): Replace deprecated `createPermissionIntegrationRouter` API call with `permissionsRegistry`
- [`b3292fc`](https://github.com/backstage/backstage/commit/b3292fc): Declare the existing per-cluster `assumeRole` and `externalId` options in the configuration schema so schema-generated configuration forms can expose AWS IAM role authentication settings. External IDs are marked as secrets.

#### 0.21.12-next.2

##### Patch Changes

- [`b3292fc`](https://github.com/backstage/backstage/commit/b3292fc): Declare the existing per-cluster `assumeRole` and `externalId` options in the configuration schema so schema-generated configuration forms can expose AWS IAM role authentication settings. External IDs are marked as secrets.

#### 0.21.11

##### Patch Changes

- [`736d84e`](https://github.com/backstage/backstage/commit/736d84e): Use locale-insensitive Unicode casing for consistent string handling across environments.
- [`1d7b704`](https://github.com/backstage/backstage/commit/1d7b704): Reject unsupported service account authentication in catalog-provided cluster definitions.
- [`b11c9b4`](https://github.com/backstage/backstage/commit/b11c9b4): Improved entity resolution on the deprecated services endpoint.
- [`5268d63`](https://github.com/backstage/backstage/commit/5268d63): Migrated tests from MSW v1 to MSW v2.
- [`ad8f2a8`](https://github.com/backstage/backstage/commit/ad8f2a8): Added actions to get kubernetes clusters and entity resources
- [`28bdf75`](https://github.com/backstage/backstage/commit/28bdf75): Improved handling of Kubernetes resource response data.
- [`97a7e8e`](https://github.com/backstage/backstage/commit/97a7e8e): The catalog cluster locator now validates Kubernetes API server URLs to block SSRF targets (non-public addresses, cloud metadata endpoints, and non-HTTPS URLs by default). Operators may list trusted hostnames in `dangerouslyAllowClusterUrls` on the catalog locator method to permit HTTP or non-public addresses for those hosts only (for example local minikube). Catalog entities cannot use the `serviceAccount` auth provider, cannot enable TLS verification skipping unless `dangerouslyAllowSkipTLSVerify` is set on the locator method, and only permitted annotations are passed through as auth metadata. Kubernetes API fetches no longer follow HTTP redirects automatically.
- [`d9a57de`](https://github.com/backstage/backstage/commit/d9a57de): Add `KubernetesWatcher` interface for streaming Kubernetes resource changes via an async iterator. The watcher is separated from `KubernetesFetcher` because watching is a long-lived streaming connection that only works with server-side auth providers. Watch supports all event types (ADDED, MODIFIED, DELETED, BOOKMARK, ERROR) with errors yielded as data rather than thrown.

#### 0.21.11-next.2

##### Patch Changes

- [`5268d63`](https://github.com/backstage/backstage/commit/5268d63): Migrated tests from MSW v1 to MSW v2.
- [`97a7e8e`](https://github.com/backstage/backstage/commit/97a7e8e): The catalog cluster locator now validates Kubernetes API server URLs to block SSRF targets (non-public addresses, cloud metadata endpoints, and non-HTTPS URLs by default). Operators may list trusted hostnames in `dangerouslyAllowClusterUrls` on the catalog locator method to permit HTTP or non-public addresses for those hosts only (for example local minikube). Catalog entities cannot use the `serviceAccount` auth provider, cannot enable TLS verification skipping unless `dangerouslyAllowSkipTLSVerify` is set on the locator method, and only permitted annotations are passed through as auth metadata. Kubernetes API fetches no longer follow HTTP redirects automatically.

#### 0.21.11-next.1

##### Patch Changes

- [`1d7b704`](https://github.com/backstage/backstage/commit/1d7b704): Reject unsupported service account authentication in catalog-provided cluster definitions.
- [`28bdf75`](https://github.com/backstage/backstage/commit/28bdf75): Improved handling of Kubernetes resource response data.

### `@backstage/plugin-kubernetes-common` (0.9.12 → [0.9.15-next.0](../../changelogs/@backstage/plugin-kubernetes-common.md#0915-next0))

#### 0.9.15-next.0

##### Patch Changes

- [`ca14116`](https://github.com/backstage/backstage/commit/ca14116): Moved `kubernetes-models` and `@kubernetes-models/apimachinery` to dev dependencies, since they are only used for types. Backends no longer install `kubernetes-models` through `@backstage/plugin-kubernetes-common`.

#### 0.9.13

##### Patch Changes

- [`d9a57de`](https://github.com/backstage/backstage/commit/d9a57de): Add `KubernetesWatcher` interface for streaming Kubernetes resource changes via an async iterator. The watcher is separated from `KubernetesFetcher` because watching is a long-lived streaming connection that only works with server-side auth providers. Watch supports all event types (ADDED, MODIFIED, DELETED, BOOKMARK, ERROR) with errors yielded as data rather than thrown.

#### 0.9.13-next.0

##### Patch Changes

- [`d9a57de`](https://github.com/backstage/backstage/commit/d9a57de): Add `KubernetesWatcher` interface for streaming Kubernetes resource changes via an async iterator. The watcher is separated from `KubernetesFetcher` because watching is a long-lived streaming connection that only works with server-side auth providers. Watch supports all event types (ADDED, MODIFIED, DELETED, BOOKMARK, ERROR) with errors yielded as data rather than thrown.

### `@backstage/plugin-kubernetes-node` (0.4.7 → [0.4.10-next.0](../../changelogs/@backstage/plugin-kubernetes-node.md#0410-next0))

#### 0.4.8

##### Patch Changes

- [`5268d63`](https://github.com/backstage/backstage/commit/5268d63): Migrated tests from MSW v1 to MSW v2.
- [`d9a57de`](https://github.com/backstage/backstage/commit/d9a57de): Add `KubernetesWatcher` interface for streaming Kubernetes resource changes via an async iterator. The watcher is separated from `KubernetesFetcher` because watching is a long-lived streaming connection that only works with server-side auth providers. Watch supports all event types (ADDED, MODIFIED, DELETED, BOOKMARK, ERROR) with errors yielded as data rather than thrown.

#### 0.4.8-next.2

##### Patch Changes

- [`5268d63`](https://github.com/backstage/backstage/commit/5268d63): Migrated tests from MSW v1 to MSW v2.

#### 0.4.8-next.0

##### Patch Changes

- [`d9a57de`](https://github.com/backstage/backstage/commit/d9a57de): Add `KubernetesWatcher` interface for streaming Kubernetes resource changes via an async iterator. The watcher is separated from `KubernetesFetcher` because watching is a long-lived streaming connection that only works with server-side auth providers. Watch supports all event types (ADDED, MODIFIED, DELETED, BOOKMARK, ERROR) with errors yielded as data rather than thrown.

### `@backstage/plugin-mcp-actions-backend` (0.2.1 → [0.2.4-next.0](../../changelogs/@backstage/plugin-mcp-actions-backend.md#024-next0))

#### 0.2.2

##### Patch Changes

- [`4a27653`](https://github.com/backstage/backstage/commit/4a27653): The default MCP server at `/api/mcp-actions/v1` is now always exposed. Previously, configuring `mcpActions.servers` replaced it, so the default endpoint was no longer served once a single named server was added. Named servers are now subsets of the default one, which continues to expose every registered action, so the same action can be exposed both there and on as many named servers as you like.

#### 0.2.2-next.1

##### Patch Changes

- [`4a27653`](https://github.com/backstage/backstage/commit/4a27653): The default MCP server at `/api/mcp-actions/v1` is now always exposed. Previously, configuring `mcpActions.servers` replaced it, so the default endpoint was no longer served once a single named server was added. Named servers are now subsets of the default one, which continues to expose every registered action, so the same action can be exposed both there and on as many named servers as you like.

### `@backstage/plugin-mui-to-bui` (0.2.10 → [0.2.13-next.0](../../changelogs/@backstage/plugin-mui-to-bui.md#0213-next0))

#### 0.2.12

##### Patch Changes

- [`701eaf4`](https://github.com/backstage/backstage/commit/701eaf4): The text now points to the main documentation instead of repeating information here.

#### 0.2.12-next.1

##### Patch Changes

- [`701eaf4`](https://github.com/backstage/backstage/commit/701eaf4): The text now points to the main documentation instead of repeating information here.

### `@backstage/plugin-notifications-backend` (0.6.8 → [0.6.11-next.0](../../changelogs/@backstage/plugin-notifications-backend.md#0611-next0))

#### 0.6.10

##### Patch Changes

- [`8ba34e8`](https://github.com/backstage/backstage/commit/8ba34e8): Persist notification payload metadata for user notifications and broadcasts, and return it when reading notifications. Re-sending a scoped notification replaces its metadata, or clears it when the new payload omits metadata.

#### 0.6.10-next.2

##### Patch Changes

- [`8ba34e8`](https://github.com/backstage/backstage/commit/8ba34e8): Persist notification payload metadata for user notifications and broadcasts, and return it when reading notifications. Re-sending a scoped notification replaces its metadata, or clears it when the new payload omits metadata.

#### 0.6.9

##### Patch Changes

- [`736d84e`](https://github.com/backstage/backstage/commit/736d84e): Use locale-insensitive Unicode casing for consistent string handling across environments.

### `@backstage/plugin-notifications-backend-module-email` (0.3.24 → [0.3.27-next.0](../../changelogs/@backstage/plugin-notifications-backend-module-email.md#0327-next0))

#### 0.3.26

##### Patch Changes

- [`663abaf`](https://github.com/backstage/backstage/commit/663abaf): Updated `nodemailer` to version 10 to address security vulnerabilities in older releases.

#### 0.3.26-next.1

##### Patch Changes

- [`663abaf`](https://github.com/backstage/backstage/commit/663abaf): Updated `nodemailer` to version 10 to address security vulnerabilities in older releases.

#### 0.3.25

##### Patch Changes

- [`041656a`](https://github.com/backstage/backstage/commit/041656a): chore(deps): bump `nodemailer` from 9.0.4 to 9.1.1
- [`2a19159`](https://github.com/backstage/backstage/commit/2a19159): Hardened notification email delivery with format validation and optional `allowedEmailDomains`. Invalid or disallowed addresses are skipped; `allowlistEmailAddresses` and `denylistEmailAddresses` match case-insensitively, allowlist still overrides the domain list, and denied addresses win last.
- [`80a548a`](https://github.com/backstage/backstage/commit/80a548a): Added `resolveNotificationLink` utility function that resolves relative notification links to absolute URLs using a provided base URL. This can be used by notification processor modules to ensure links are absolute before forwarding them to external systems.

#### 0.3.25-next.1

##### Patch Changes

- [`80a548a`](https://github.com/backstage/backstage/commit/80a548a): Added `resolveNotificationLink` utility function that resolves relative notification links to absolute URLs using a provided base URL. This can be used by notification processor modules to ensure links are absolute before forwarding them to external systems.

#### 0.3.25-next.0

##### Patch Changes

- [`2a19159`](https://github.com/backstage/backstage/commit/2a19159): Hardened notification email delivery with format validation and optional `allowedEmailDomains`. Invalid or disallowed addresses are skipped; `allowlistEmailAddresses` and `denylistEmailAddresses` match case-insensitively, allowlist still overrides the domain list, and denied addresses win last.

### `@backstage/plugin-notifications-backend-module-slack` (0.4.5 → [0.4.8-next.0](../../changelogs/@backstage/plugin-notifications-backend-module-slack.md#048-next0))

#### 0.4.6

##### Patch Changes

- [`0325d26`](https://github.com/backstage/backstage/commit/0325d26): chore(deps-dev): bump `@faker-js/faker` from 10.4.0 to 10.5.0
- [`80a548a`](https://github.com/backstage/backstage/commit/80a548a): Added `resolveNotificationLink` utility function that resolves relative notification links to absolute URLs using a provided base URL. This can be used by notification processor modules to ensure links are absolute before forwarding them to external systems.

#### 0.4.6-next.1

##### Patch Changes

- [`80a548a`](https://github.com/backstage/backstage/commit/80a548a): Added `resolveNotificationLink` utility function that resolves relative notification links to absolute URLs using a provided base URL. This can be used by notification processor modules to ensure links are absolute before forwarding them to external systems.

### `@backstage/plugin-notifications-node` (0.2.29 → [0.2.32-next.0](../../changelogs/@backstage/plugin-notifications-node.md#0232-next0))

#### 0.2.30

##### Patch Changes

- [`80a548a`](https://github.com/backstage/backstage/commit/80a548a): Added `resolveNotificationLink` utility function that resolves relative notification links to absolute URLs using a provided base URL. This can be used by notification processor modules to ensure links are absolute before forwarding them to external systems.

#### 0.2.30-next.1

##### Patch Changes

- [`80a548a`](https://github.com/backstage/backstage/commit/80a548a): Added `resolveNotificationLink` utility function that resolves relative notification links to absolute URLs using a provided base URL. This can be used by notification processor modules to ensure links are absolute before forwarding them to external systems.

### `@backstage/plugin-proxy-backend` (0.6.17 → [0.6.20-next.0](../../changelogs/@backstage/plugin-proxy-backend.md#0620-next0))

#### 0.6.18

##### Patch Changes

- [`736d84e`](https://github.com/backstage/backstage/commit/736d84e): Use locale-insensitive Unicode casing for consistent string handling across environments.
- [`42580a2`](https://github.com/backstage/backstage/commit/42580a2): Improved request path handling in the proxy-backend.
- [`9df9292`](https://github.com/backstage/backstage/commit/9df9292): Ensure HTTP proxy requests consistently apply their configured credential requirements.

#### 0.6.18-next.0

##### Patch Changes

- [`42580a2`](https://github.com/backstage/backstage/commit/42580a2): Improved request path handling in the proxy-backend.

### `@backstage/plugin-scaffolder-backend-module-azure` (0.2.25 → [0.2.28-next.0](../../changelogs/@backstage/plugin-scaffolder-backend-module-azure.md#0228-next0))

#### 0.2.26

##### Patch Changes

- [`bbba6b5`](https://github.com/backstage/backstage/commit/bbba6b5): Added support for requiring user-provided credentials for Azure DevOps mutation actions when `scaffolder.requireScmUserCredentials` is enabled.

#### 0.2.26-next.1

##### Patch Changes

- [`bbba6b5`](https://github.com/backstage/backstage/commit/bbba6b5): Added support for requiring user-provided credentials for Azure DevOps mutation actions when `scaffolder.requireScmUserCredentials` is enabled.

### `@backstage/plugin-scaffolder-backend-module-bitbucket-cloud` (0.3.10 → [0.3.13-next.0](../../changelogs/@backstage/plugin-scaffolder-backend-module-bitbucket-cloud.md#0313-next0))

#### 0.3.11

##### Patch Changes

- [`40c64a0`](https://github.com/backstage/backstage/commit/40c64a0): Fixed a security issue in pull request workspace handling.
- [`bbba6b5`](https://github.com/backstage/backstage/commit/bbba6b5): Added support for requiring user-provided credentials for Bitbucket Cloud mutation actions when `scaffolder.requireScmUserCredentials` is enabled.

#### 0.3.11-next.1

##### Patch Changes

- [`40c64a0`](https://github.com/backstage/backstage/commit/40c64a0): Fixed a security issue in pull request workspace handling.
- [`bbba6b5`](https://github.com/backstage/backstage/commit/bbba6b5): Added support for requiring user-provided credentials for Bitbucket Cloud mutation actions when `scaffolder.requireScmUserCredentials` is enabled.

### `@backstage/plugin-scaffolder-backend-module-bitbucket-server` (0.2.25 → [0.2.28-next.0](../../changelogs/@backstage/plugin-scaffolder-backend-module-bitbucket-server.md#0228-next0))

#### 0.2.26

##### Patch Changes

- [`40c64a0`](https://github.com/backstage/backstage/commit/40c64a0): Fixed a security issue in pull request workspace handling.
- [`bbba6b5`](https://github.com/backstage/backstage/commit/bbba6b5): Added support for requiring user-provided credentials for Bitbucket Server mutation actions when `scaffolder.requireScmUserCredentials` is enabled.

#### 0.2.26-next.1

##### Patch Changes

- [`40c64a0`](https://github.com/backstage/backstage/commit/40c64a0): Fixed a security issue in pull request workspace handling.
- [`bbba6b5`](https://github.com/backstage/backstage/commit/bbba6b5): Added support for requiring user-provided credentials for Bitbucket Server mutation actions when `scaffolder.requireScmUserCredentials` is enabled.

### `@backstage/plugin-scaffolder-backend-module-confluence-to-markdown` (0.3.25 → [0.3.28-next.0](../../changelogs/@backstage/plugin-scaffolder-backend-module-confluence-to-markdown.md#0328-next0))

#### 0.3.26

##### Patch Changes

- [`6e11531`](https://github.com/backstage/backstage/commit/6e11531): Improve handling of imported Confluence attachments
- [`3026628`](https://github.com/backstage/backstage/commit/3026628): Validate repository file paths before transforming Confluence content.

#### 0.3.26-next.1

##### Patch Changes

- [`6e11531`](https://github.com/backstage/backstage/commit/6e11531): Improve handling of imported Confluence attachments
- [`3026628`](https://github.com/backstage/backstage/commit/3026628): Validate repository file paths before transforming Confluence content.

### `@backstage/plugin-scaffolder-node` (0.13.6 → [0.13.9-next.0](../../changelogs/@backstage/plugin-scaffolder-node.md#0139-next0))

#### 0.13.7

##### Patch Changes

- [`3bb3710`](https://github.com/backstage/backstage/commit/3bb3710): Added optional cancellation support when waiting to claim a scaffolder task.
- [`e95b649`](https://github.com/backstage/backstage/commit/e95b649): Added task recovery feature with new `scaffolder.taskRecovery` config section. When enabled, tasks that crash or timeout are automatically recovered and resume from the last completed step, task secrets are retained until the task reaches a terminal state so recovery can continue, and completed step outputs are persisted. Enabling recovery applies to all scaffolder tasks, so actions used by those tasks should be idempotent or use checkpoints. When recovery is disabled (the default), the previous behavior is unchanged: secrets are cleared as soon as a task is claimed and retries re-run every step. The new config consolidates previous experimental flags (`EXPERIMENTAL_recoverTasks`, `EXPERIMENTAL_workspaceSerialization`, `EXPERIMENTAL_recoverTasksTimeout`) which remain supported as fallbacks. The legacy workspace provider setting continues to select a provider only when `EXPERIMENTAL_workspaceSerialization` is `true`.

  Workspace serialization for task recovery now requires installing a separate workspace provider module, including when you use the legacy configuration. For development, use `@backstage/plugin-scaffolder-backend-module-workspace-database` (50 MB limit, not recommended for production). On first startup, that module migrates existing database workspace snapshots from the legacy task storage. For production, use `@backstage/plugin-scaffolder-backend-module-gcp` or a similar external storage provider. The scaffolder rejects a configured provider that has not been installed and registered.

  Enabling crash recovery does not keep completed task event streams open; normal task completion remains terminal for event-stream clients.

#### 0.13.7-next.2

##### Patch Changes

- [`3bb3710`](https://github.com/backstage/backstage/commit/3bb3710): Added optional cancellation support when waiting to claim a scaffolder task.

#### 0.13.7-next.0

##### Patch Changes

- [`e95b649`](https://github.com/backstage/backstage/commit/e95b649): Added task recovery feature with new `scaffolder.taskRecovery` config section. When enabled, tasks that crash or timeout are automatically recovered and resume from the last completed step, task secrets are retained until the task reaches a terminal state so recovery can continue, and completed step outputs are persisted. Enabling recovery applies to all scaffolder tasks, so actions used by those tasks should be idempotent or use checkpoints. When recovery is disabled (the default), the previous behavior is unchanged: secrets are cleared as soon as a task is claimed and retries re-run every step. The new config consolidates previous experimental flags (`EXPERIMENTAL_recoverTasks`, `EXPERIMENTAL_workspaceSerialization`, `EXPERIMENTAL_recoverTasksTimeout`) which remain supported as fallbacks. The legacy workspace provider setting continues to select a provider only when `EXPERIMENTAL_workspaceSerialization` is `true`.

  Workspace serialization for task recovery now requires installing a separate workspace provider module, including when you use the legacy configuration. For development, use `@backstage/plugin-scaffolder-backend-module-workspace-database` (50 MB limit, not recommended for production). On first startup, that module migrates existing database workspace snapshots from the legacy task storage. For production, use `@backstage/plugin-scaffolder-backend-module-gcp` or a similar external storage provider. The scaffolder rejects a configured provider that has not been installed and registered.

  Enabling crash recovery does not keep completed task event streams open; normal task completion remains terminal for event-stream clients.

### `@backstage/plugin-search-backend-module-catalog` (0.3.18 → [0.3.21-next.0](../../changelogs/@backstage/plugin-search-backend-module-catalog.md#0321-next0))

#### 0.3.19

##### Patch Changes

- [`979c255`](https://github.com/backstage/backstage/commit/979c255): Improved catalog indexing performance by using cursor pagination for TechDocs and avoiding unused total item counts in search collators.

#### 0.3.19-next.0

##### Patch Changes

- [`979c255`](https://github.com/backstage/backstage/commit/979c255): Improved catalog indexing performance by using cursor pagination for TechDocs and avoiding unused total item counts in search collators.

### `@backstage/plugin-search-backend-module-explore` (0.3.17 → [0.3.20-next.0](../../changelogs/@backstage/plugin-search-backend-module-explore.md#0320-next0))

#### 0.3.19

##### Patch Changes

- [`33ff9ed`](https://github.com/backstage/backstage/commit/33ff9ed): Updated dependency `@backstage-community/plugin-explore-common` to `^0.14.0`.

#### 0.3.19-next.1

##### Patch Changes

- [`33ff9ed`](https://github.com/backstage/backstage/commit/33ff9ed): Updated dependency `@backstage-community/plugin-explore-common` to `^0.14.0`.

### `@backstage/plugin-search-backend-module-pg` (0.5.58 → [0.5.61-next.0](../../changelogs/@backstage/plugin-search-backend-module-pg.md#0561-next0))

#### 0.5.60

##### Patch Changes

- [`7535616`](https://github.com/backstage/backstage/commit/7535616): Fixed PostgreSQL search highlighting when configured delimiters or selection tags contain punctuation that requires quoting.

#### 0.5.60-next.0

##### Patch Changes

- [`7535616`](https://github.com/backstage/backstage/commit/7535616): Fixed PostgreSQL search highlighting when configured delimiters or selection tags contain punctuation that requires quoting.

### `@backstage/plugin-search-backend-module-techdocs` (0.4.17 → [0.4.20-next.0](../../changelogs/@backstage/plugin-search-backend-module-techdocs.md#0420-next0))

#### 0.4.18

##### Patch Changes

- [`736d84e`](https://github.com/backstage/backstage/commit/736d84e): Use locale-insensitive Unicode casing for consistent string handling across environments.
- [`979c255`](https://github.com/backstage/backstage/commit/979c255): Improved catalog indexing performance by using cursor pagination for TechDocs and avoiding unused total item counts in search collators.

#### 0.4.18-next.0

##### Patch Changes

- [`979c255`](https://github.com/backstage/backstage/commit/979c255): Improved catalog indexing performance by using cursor pagination for TechDocs and avoiding unused total item counts in search collators.

### `@backstage/plugin-signals-backend` (0.3.18 → [0.3.21-next.0](../../changelogs/@backstage/plugin-signals-backend.md#0321-next0))

#### 0.3.20

##### Patch Changes

- [`e956084`](https://github.com/backstage/backstage/commit/e956084): Use the backend instance ID to identify the event subscription, allowing deployments to control how Signals instances fan out events.
- [`3873113`](https://github.com/backstage/backstage/commit/3873113): The signals WebSocket endpoint now requires a valid user identity token. The token can appear anywhere in the requested WebSocket protocols. Connections without a token, with an invalid token, or with a non-user (service) token are rejected, and unauthenticated guest connections are no longer accepted.

#### 0.3.20-next.2

##### Patch Changes

- [`3873113`](https://github.com/backstage/backstage/commit/3873113): The signals WebSocket endpoint now requires a valid user identity token. The token can appear anywhere in the requested WebSocket protocols. Connections without a token, with an invalid token, or with a non-user (service) token are rejected, and unauthenticated guest connections are no longer accepted.

#### 0.3.20-next.1

##### Patch Changes

- [`e956084`](https://github.com/backstage/backstage/commit/e956084): Use the backend instance ID to identify the event subscription, allowing deployments to control how Signals instances fan out events.

#### 0.3.19

##### Patch Changes

- [`0ae9229`](https://github.com/backstage/backstage/commit/0ae9229): Fixed WebSocket upgrade error responses to prevent load balancers from returning 502 when authentication fails. Error responses now use valid HTTP headers, ensuring the actual error status (401 or 500) is delivered to the client instead of being masked.

### `@backstage/plugin-techdocs-common` (0.1.1 → [0.1.2](../../changelogs/@backstage/plugin-techdocs-common.md#012))

#### 0.1.2

##### Patch Changes

- [`45b0b89`](https://github.com/backstage/backstage/commit/45b0b89): Added a new `techdocs.actions.read` permission, available from the `/alpha` entry point, which controls access to the TechDocs actions registered with the Actions Registry.

### `@backstage/plugin-user-settings` (0.9.6 → [0.9.9-next.0](../../changelogs/@backstage/plugin-user-settings.md#099-next0))

#### 0.9.7

##### Patch Changes

- [`736d84e`](https://github.com/backstage/backstage/commit/736d84e): Use locale-insensitive Unicode casing for consistent string handling across environments.
- [`d421187`](https://github.com/backstage/backstage/commit/d421187): Reduced the initial app bundle size by loading page and optional UI implementations only when their extensions render.

#### 0.9.7-next.1

##### Patch Changes

- [`d421187`](https://github.com/backstage/backstage/commit/d421187): Reduced the initial app bundle size by loading page and optional UI implementations only when their extensions render.

### `@backstage/repo-tools` (0.19.0 → [0.19.3-next.0](../../changelogs/@backstage/repo-tools.md#0193-next0))

#### 0.19.2

##### Patch Changes

- [`b8c8132`](https://github.com/backstage/backstage/commit/b8c8132): CLI API reports now support help output with separate groups and commands sections, including commands nested within groups.
- [`76ac6ed`](https://github.com/backstage/backstage/commit/76ac6ed): Updated dependency `js-yaml` to `^5.0.0`.
- [`466bbea`](https://github.com/backstage/backstage/commit/466bbea): Fixed CLI report generation failing when the `FORCE_COLOR` environment variable is set.
- [`dec6175`](https://github.com/backstage/backstage/commit/dec6175): When an API, CLI, SQL, or knip report is out of date in CI, the error output now shows a diff of the changes that need to be committed instead of printing the full expected report.
- [`a281164`](https://github.com/backstage/backstage/commit/a281164): Updated SQL report generation to support newer Knex releases.

#### 0.19.2-next.3

##### Patch Changes

- [`dec6175`](https://github.com/backstage/backstage/commit/dec6175): When an API, CLI, SQL, or knip report is out of date in CI, the error output now shows a diff of the changes that need to be committed instead of printing the full expected report.

#### 0.19.2-next.2

##### Patch Changes

- [`b8c8132`](https://github.com/backstage/backstage/commit/b8c8132): CLI API reports now support help output with separate groups and commands sections, including commands nested within groups.
- [`76ac6ed`](https://github.com/backstage/backstage/commit/76ac6ed): Updated dependency `js-yaml` to `^5.0.0`.

#### 0.19.2-next.0

##### Patch Changes

- [`a281164`](https://github.com/backstage/backstage/commit/a281164): Updated SQL report generation to support newer Knex releases.

#### 0.19.1

##### Patch Changes

- [`736d84e`](https://github.com/backstage/backstage/commit/736d84e): Use locale-insensitive Unicode casing for consistent string handling across environments.
- [`c0ebaa7`](https://github.com/backstage/backstage/commit/c0ebaa7): chore(deps): bump `js-yaml` from 4.3.1 to 4.3.2
- [`bf1f82d`](https://github.com/backstage/backstage/commit/bf1f82d): Added the required OpenAPI types dependency for Swagger Parser.
- [`0c1b8ee`](https://github.com/backstage/backstage/commit/0c1b8ee): Updated the OpenAPI generator tooling to avoid known security vulnerabilities.

#### 0.19.1-next.1

##### Patch Changes

- [`0c1b8ee`](https://github.com/backstage/backstage/commit/0c1b8ee): Updated the OpenAPI generator tooling to avoid known security vulnerabilities.

#### 0.19.1-next.0

##### Patch Changes

- [`bf1f82d`](https://github.com/backstage/backstage/commit/bf1f82d): Added the required OpenAPI types dependency for Swagger Parser.

## Other minor version bumps

### `@backstage/backend-app-api` (1.7.3 → [1.9.0-next.0](../../changelogs/@backstage/backend-app-api.md#190-next0))

#### 1.9.0-next.0

##### Minor Changes

- [`1c93987`](https://github.com/backstage/backstage/commit/1c93987): Add optional `beginAt` timestamps to `PluginStartupResult` and `ModuleStartupResult` in the `BackendStartupResult` returned by `backend.start()`. The new timestamp marks when a plugin's or module's init function was invoked, i.e. after its dependencies were resolved. Together with the existing `resultAt` this makes it possible to see how long each individual plugin's or module's init function took, separate from time spent waiting for other plugins to initialize. It is undefined when a plugin or module failed before reaching initialization.

#### 1.8.0

##### Minor Changes

- [`e956084`](https://github.com/backstage/backstage/commit/e956084): Added an `instanceId` option to `createSpecializedBackend`. Each backend instance uses a random UUID by default.

##### Patch Changes

- [`f6054ac`](https://github.com/backstage/backstage/commit/f6054ac): Updated undeclared-connection errors to direct plugin authors to `declareConnection` from `@backstage/backend-plugin-api/alpha`.

#### 1.8.0-next.2

##### Patch Changes

- [`f6054ac`](https://github.com/backstage/backstage/commit/f6054ac): Updated undeclared-connection errors to direct plugin authors to `declareConnection` from `@backstage/backend-plugin-api/alpha`.

#### 1.8.0-next.1

##### Minor Changes

- [`e956084`](https://github.com/backstage/backstage/commit/e956084): Added an `instanceId` option to `createSpecializedBackend`. Each backend instance uses a random UUID by default.

### `@backstage/plugin-catalog-common` (1.1.10 → [1.2.1](../../changelogs/@backstage/plugin-catalog-common.md#121))

#### 1.2.0

##### Minor Changes

- [`305e2f7`](https://github.com/backstage/backstage/commit/305e2f7): Added permissions for reading and managing catalog ingestion providers.

### `@backstage/plugin-scaffolder` (1.38.2 → [1.41.0-next.0](../../changelogs/@backstage/plugin-scaffolder.md#1410-next0))

#### 1.41.0-next.0

##### Minor Changes

- [`3fe82f6`](https://github.com/backstage/backstage/commit/3fe82f6): Added a `ScaffolderTemplateFilterBlueprint` that lets apps filter the new frontend system's template list using identity, catalog, or other viewer-specific state.
- [`ae86338`](https://github.com/backstage/backstage/commit/ae86338): Added GitLab branch autocompletion to RepoBranchPicker using user SCM credentials.

##### Patch Changes

- [`111c6ce`](https://github.com/backstage/backstage/commit/111c6ce): Keep the task button bar at the user's chosen visibility when a task completes, so log visibility and start-over controls remain accessible. Action availability continues to depend on task state and permissions.

#### 1.40.0

##### Minor Changes

- [`d0cc453`](https://github.com/backstage/backstage/commit/d0cc453): Added a `Featured Templates` homepage widget that displays templates tagged with a configurable catalog tag, defaulting to `featured`.

#### 1.40.0-next.2

##### Minor Changes

- [`d0cc453`](https://github.com/backstage/backstage/commit/d0cc453): Added a `Featured Templates` homepage widget that displays templates tagged with a configurable catalog tag, defaulting to `featured`.

#### 1.39.0

##### Minor Changes

- [`1b99861`](https://github.com/backstage/backstage/commit/1b99861): The `sub-page:scaffolder/templates` extension now accepts a `templateFilter` field that lets you filter which templates are shown on the template list page.
- [`e060bd4`](https://github.com/backstage/backstage/commit/e060bd4): Added new `ui:options` to `RepoUrlPicker` for per-template customization: `ownerLabel`, `ownerDescription`, `repoLabel`, `repoDescription` to override field labels, and `disableRepoAutocomplete` to render a plain text input instead of the autocomplete dropdown.
- [`5ff93bf`](https://github.com/backstage/backstage/commit/5ff93bf): Added functionality to register a Template Outputs Component in the new frontend system.

##### Patch Changes

- [`736d84e`](https://github.com/backstage/backstage/commit/736d84e): Use locale-insensitive Unicode casing for consistent string handling across environments.
- [`cfba1bc`](https://github.com/backstage/backstage/commit/cfba1bc): Updated internal type definitions. No changes to runtime behavior or public API.

#### 1.39.0-next.2

##### Patch Changes

- [`cfba1bc`](https://github.com/backstage/backstage/commit/cfba1bc): Updated internal type definitions. No changes to runtime behavior or public API.

#### 1.39.0-next.0

##### Minor Changes

- [`5ff93bf`](https://github.com/backstage/backstage/commit/5ff93bf): Added functionality to register a Template Outputs Component in the new frontend system.

### `@backstage/plugin-scaffolder-backend` (4.1.0 → [4.2.2-next.0](../../changelogs/@backstage/plugin-scaffolder-backend.md#422-next0))

#### 4.2.2-next.0

##### Patch Changes

- [`be5074c`](https://github.com/backstage/backstage/commit/be5074c): Preserve public task log values when rendering without secrets omits an earlier object field, while continuing to redact secret-derived keys and values.
- [`62eaba9`](https://github.com/backstage/backstage/commit/62eaba9): Fixed custom task permission rules registered by backend modules being ignored when authorizing task access and filtering task lists.

#### 4.2.1

##### Patch Changes

- [`6e08d65`](https://github.com/backstage/backstage/commit/6e08d65): Fixes a regression where scaffolder step values consisting of a singular template statement block (ex. `if: "{% if parameters.foo == 'bar' %}true{% else %}false{% endif %}"`), were rendered as the strings `"true"` and `"false"` instead of their boolean values. This caused steps with `if` conditions to always run.

  Step values with a single statement block that renders nothing, such as `{% if false %}x{% endif %}`, are once again left out of the action input instead of being passed as an empty string.

  Updated `nunjitsu` to `^0.6.2`.

#### 4.2.0

##### Minor Changes

- [`09f42dd`](https://github.com/backstage/backstage/commit/09f42dd): export workspace:template\* actions by default
- [`1a705ca`](https://github.com/backstage/backstage/commit/1a705ca): Applied `templateDryRunPermission` to inline Software Template dry runs and the corresponding backend action. Permission policies that deny unknown permissions must explicitly allow `scaffolder.template.dry-run` to retain existing dry-run access.
- [`e95b649`](https://github.com/backstage/backstage/commit/e95b649): Added task recovery feature with new `scaffolder.taskRecovery` config section. When enabled, tasks that crash or timeout are automatically recovered and resume from the last completed step, task secrets are retained until the task reaches a terminal state so recovery can continue, and completed step outputs are persisted. Enabling recovery applies to all scaffolder tasks, so actions used by those tasks should be idempotent or use checkpoints. When recovery is disabled (the default), the previous behavior is unchanged: secrets are cleared as soon as a task is claimed and retries re-run every step. The new config consolidates previous experimental flags (`EXPERIMENTAL_recoverTasks`, `EXPERIMENTAL_workspaceSerialization`, `EXPERIMENTAL_recoverTasksTimeout`) which remain supported as fallbacks. The legacy workspace provider setting continues to select a provider only when `EXPERIMENTAL_workspaceSerialization` is `true`.

  Workspace serialization for task recovery now requires installing a separate workspace provider module, including when you use the legacy configuration. For development, use `@backstage/plugin-scaffolder-backend-module-workspace-database` (50 MB limit, not recommended for production). On first startup, that module migrates existing database workspace snapshots from the legacy task storage. For production, use `@backstage/plugin-scaffolder-backend-module-gcp` or a similar external storage provider. The scaffolder rejects a configured provider that has not been installed and registered.

  Enabling crash recovery does not keep completed task event streams open; normal task completion remains terminal for event-stream clients.

- [`bbba6b5`](https://github.com/backstage/backstage/commit/bbba6b5): Added the `scaffolder.requireScmUserCredentials` configuration option to require user-provided credentials for supported SCM mutation and fetch actions.

##### Patch Changes

- [`736d84e`](https://github.com/backstage/backstage/commit/736d84e): Use locale-insensitive Unicode casing for consistent string handling across environments.
- [`7fba55a`](https://github.com/backstage/backstage/commit/7fba55a): Removed user entity references from scaffolder task count metrics to avoid exposing user identities and creating high-cardinality metric labels.
- [`b1256aa`](https://github.com/backstage/backstage/commit/b1256aa): Respect task read permission decisions when listing scaffolder tasks.
- [`15fa029`](https://github.com/backstage/backstage/commit/15fa029): Restrict task list ordering to supported fields.
- [`be0a75a`](https://github.com/backstage/backstage/commit/be0a75a): Exclude internal task data from task responses.
- [`2bf1392`](https://github.com/backstage/backstage/commit/2bf1392): Software template inline conditionals without an `else` branch now render an empty string when their condition is false, matching Nunjucks behavior.
- [`3bb3710`](https://github.com/backstage/backstage/commit/3bb3710): Improved task worker resilience by backing off repeated database claim failures, containing unexpected task execution errors, and preventing new work from being claimed during graceful shutdown.
- [`beaa3db`](https://github.com/backstage/backstage/commit/beaa3db): Reject Scaffolder steps where `each` resolves to a primitive value instead of an array or object.
- [`f389dd2`](https://github.com/backstage/backstage/commit/f389dd2): Improve denied scaffolder action error handling.
- [`2eebeb7`](https://github.com/backstage/backstage/commit/2eebeb7): Ensure task failure details use the configured log redactions.
- [`84ebbb9`](https://github.com/backstage/backstage/commit/84ebbb9): Fixed log redaction for transformed secret values used to iterate Scaffolder steps.
- [`b4172dd`](https://github.com/backstage/backstage/commit/b4172dd): Restrict task retries to terminal states.
- [`c1a30ef`](https://github.com/backstage/backstage/commit/c1a30ef): Restored support for intrinsic string, number, array, `Map`, and `Set` methods in software templates.
- [`ee9c48d`](https://github.com/backstage/backstage/commit/ee9c48d): Fixed matching of action input values in scaffolder permission policies.
- [`79f0b91`](https://github.com/backstage/backstage/commit/79f0b91): Fixed the scaffolder task worker silently giving up after a transient failure. A single error while picking up a task, such as a dropped database connection, would stop the backend from running any further software templates for the rest of its lifetime. New tasks stayed queued indefinitely with no error shown to the user and no failing health check, and the only way to recover was to restart the backend. Picking up tasks is now retried instead.

#### 4.2.0-next.2

##### Patch Changes

- [`3bb3710`](https://github.com/backstage/backstage/commit/3bb3710): Improved task worker resilience by backing off repeated database claim failures, containing unexpected task execution errors, and preventing new work from being claimed during graceful shutdown.

#### 4.2.0-next.1

##### Minor Changes

- [`bbba6b5`](https://github.com/backstage/backstage/commit/bbba6b5): Added the `scaffolder.requireScmUserCredentials` configuration option to require user-provided credentials for supported SCM mutation and fetch actions.

##### Patch Changes

- [`7fba55a`](https://github.com/backstage/backstage/commit/7fba55a): Removed user entity references from scaffolder task count metrics to avoid exposing user identities and creating high-cardinality metric labels.
- [`b1256aa`](https://github.com/backstage/backstage/commit/b1256aa): Respect task read permission decisions when listing scaffolder tasks.
- [`15fa029`](https://github.com/backstage/backstage/commit/15fa029): Restrict task list ordering to supported fields.
- [`be0a75a`](https://github.com/backstage/backstage/commit/be0a75a): Exclude internal task data from task responses.
- [`f389dd2`](https://github.com/backstage/backstage/commit/f389dd2): Improve denied scaffolder action error handling.
- [`2eebeb7`](https://github.com/backstage/backstage/commit/2eebeb7): Ensure task failure details use the configured log redactions.
- [`84ebbb9`](https://github.com/backstage/backstage/commit/84ebbb9): Fixed log redaction for transformed secret values used to iterate Scaffolder steps.
- [`b4172dd`](https://github.com/backstage/backstage/commit/b4172dd): Restrict task retries to terminal states.
- [`ee9c48d`](https://github.com/backstage/backstage/commit/ee9c48d): Fixed matching of action input values in scaffolder permission policies.
- [`79f0b91`](https://github.com/backstage/backstage/commit/79f0b91): Fixed the scaffolder task worker silently giving up after a transient failure. A single error while picking up a task, such as a dropped database connection, would stop the backend from running any further software templates for the rest of its lifetime. New tasks stayed queued indefinitely with no error shown to the user and no failing health check, and the only way to recover was to restart the backend. Picking up tasks is now retried instead.

### `@backstage/plugin-scaffolder-common` (2.2.3 → [2.3.1](../../changelogs/@backstage/plugin-scaffolder-common.md#231))

#### 2.3.0

##### Minor Changes

- [`1a705ca`](https://github.com/backstage/backstage/commit/1a705ca): Added `templateDryRunPermission`, which allows permission policies to control who can submit inline Software Template dry runs.

##### Patch Changes

- [`be0a75a`](https://github.com/backstage/backstage/commit/be0a75a): Exclude internal task data from task responses.
- [`ffaca06`](https://github.com/backstage/backstage/commit/ffaca06): Fixed a connection leak in the scaffolder event stream where unsubscribing did not abort the underlying SSE connection. Also changed unexpected server disconnects to signal an error instead of silently completing, enabling consumers to retry.

### `@backstage/plugin-techdocs` (1.18.0 → [1.19.1-next.0](../../changelogs/@backstage/plugin-techdocs.md#1191-next0))

#### 1.19.1-next.0

##### Patch Changes

- [`9a1d5cf`](https://github.com/backstage/backstage/commit/9a1d5cf): Fixed the TechDocs table of contents drifting to the right on wide screens. It now stays aligned with the right edge of the documentation content.

#### 1.19.0

##### Minor Changes

- [`4a5b52d`](https://github.com/backstage/backstage/commit/4a5b52d): TechDocs now uses the default `NotFoundErrorPage` when documentation is missing, instead of its own TechDocs-specific page.

  This means if you have provided an override to the `NotFoundErrorPage` component it will now be used within TechDocs when documentation is missing as well.

  One thing to note is that the default not found page shows "PAGE NOT FOUND" rather than "Documentation not found".

- [`80a0da9`](https://github.com/backstage/backstage/commit/80a0da9): Added `withoutFeedbackLink` prop to `page:techdocs/reader` and `entity-content:techdocs` extensions, which can be set to `true` to disable the feedback button in the rendered documentation.

##### Patch Changes

- [`24fd0e8`](https://github.com/backstage/backstage/commit/24fd0e8): Fixed TechDocs addons silently not rendering in apps using the new frontend system, on both the standalone documentation reader page and the entity documentation tab.
- [`6c74f3f`](https://github.com/backstage/backstage/commit/6c74f3f): Migrated the `TechDocsPicker` filter from the deprecated `getCatalogFilters` to `getCatalogQuery`.

#### 1.19.0-next.2

##### Patch Changes

- [`6c74f3f`](https://github.com/backstage/backstage/commit/6c74f3f): Migrated the `TechDocsPicker` filter from the deprecated `getCatalogFilters` to `getCatalogQuery`.

#### 1.19.0-next.1

##### Minor Changes

- [`4a5b52d`](https://github.com/backstage/backstage/commit/4a5b52d): TechDocs now uses the default `NotFoundErrorPage` when documentation is missing, instead of its own TechDocs-specific page.

  This means if you have provided an override to the `NotFoundErrorPage` component it will now be used within TechDocs when documentation is missing as well.

  One thing to note is that the default not found page shows "PAGE NOT FOUND" rather than "Documentation not found".

#### 1.19.0-next.0

##### Minor Changes

- [`80a0da9`](https://github.com/backstage/backstage/commit/80a0da9): Added `withoutFeedbackLink` prop to `page:techdocs/reader` and `entity-content:techdocs` extensions, which can be set to `true` to disable the feedback button in the rendered documentation.

##### Patch Changes

- [`24fd0e8`](https://github.com/backstage/backstage/commit/24fd0e8): Fixed TechDocs addons silently not rendering in apps using the new frontend system, on both the standalone documentation reader page and the entity documentation tab.

#### 1.18.1

##### Patch Changes

- [`736d84e`](https://github.com/backstage/backstage/commit/736d84e): Use locale-insensitive Unicode casing for consistent string handling across environments.
- [`d421187`](https://github.com/backstage/backstage/commit/d421187): Reduced the initial app bundle size by loading page and optional UI implementations only when their extensions render.
- [`9cb79f5`](https://github.com/backstage/backstage/commit/9cb79f5): Use the catalog presentation API for TechDocs document titles and owner labels so entity display names are consistent with the rest of Backstage.

#### 1.18.1-next.1

##### Patch Changes

- [`d421187`](https://github.com/backstage/backstage/commit/d421187): Reduced the initial app bundle size by loading page and optional UI implementations only when their extensions render.
- [`9cb79f5`](https://github.com/backstage/backstage/commit/9cb79f5): Use the catalog presentation API for TechDocs document titles and owner labels so entity display names are consistent with the rest of Backstage.

### `@backstage/plugin-techdocs-backend` (2.2.4 → [2.4.1-next.0](../../changelogs/@backstage/plugin-techdocs-backend.md#241-next0))

#### 2.4.1-next.0

##### Patch Changes

- [`4d7a3fe`](https://github.com/backstage/backstage/commit/4d7a3fe): Clarified in the config schema which `techdocs.generator.mkdocs` settings also apply to the Zensical engine: `legacyCopyReadmeMdToIndexMd`, `dangerouslyAllowAdditionalKeys` and `dangerouslyAllowAdditionalPlugins`.

#### 2.4.0

##### Minor Changes

- [`4d4f987`](https://github.com/backstage/backstage/commit/4d4f987): Add engine abstraction layer for multi-engine TechDocs support. Introduces `--engine` flag, engine config map, generator registry with `backstage.io/techdocs-engine` annotation support, `engine` field in `techdocs_metadata.json`, `serve:raw` command, and live-reload adapter interface. MkDocs remains the default with no behavior change.

  The built-in generator is now registered under `mkdocs`; the previous `techdocs` key is kept as an alias, so existing `generators.register('techdocs', ...)` calls continue to work. The CLI's `--engine` flag takes precedence over the `backstage.io/techdocs-engine` annotation for all commands, and `serve:mkdocs` and the `--mkdocs-parameter-*` flags now print deprecation warnings.

- [`45b0b89`](https://github.com/backstage/backstage/commit/45b0b89): Added a `get-techdocs-metadata` action to the TechDocs backend plugin, registered with the Actions Registry Service (alpha).

##### Patch Changes

- [`685aee1`](https://github.com/backstage/backstage/commit/685aee1): Fixed TechDocs asset caching on reused HTTP connections to avoid listener leaks and cross-request response corruption. Existing cached assets are refreshed automatically.

#### 2.4.0-next.2

##### Minor Changes

- [`45b0b89`](https://github.com/backstage/backstage/commit/45b0b89): Added a `get-techdocs-metadata` action to the TechDocs backend plugin, registered with the Actions Registry Service (alpha).

##### Patch Changes

- [`685aee1`](https://github.com/backstage/backstage/commit/685aee1): Fixed TechDocs asset caching on reused HTTP connections to avoid listener leaks and cross-request response corruption. Existing cached assets are refreshed automatically.

#### 2.3.0

##### Minor Changes

- [`ee97130`](https://github.com/backstage/backstage/commit/ee97130): Added support for `techdocs.generator.pullOptions` when pulling the TechDocs generator Docker image from private registries that require authentication.
- [`62d1a6f`](https://github.com/backstage/backstage/commit/62d1a6f): Added `techdocs.generator.mkdocs.dangerouslyAllowAdditionalPlugins` configuration option, allowing operators to extend the set of permitted MkDocs plugins during TechDocs generation.

##### Patch Changes

- [`932986c`](https://github.com/backstage/backstage/commit/932986c): Improve validation of TechDocs static content paths.
- [`736d84e`](https://github.com/backstage/backstage/commit/736d84e): Use locale-insensitive Unicode casing for consistent string handling across environments.
- [`1b0e277`](https://github.com/backstage/backstage/commit/1b0e277): Improved path validation for TechDocs content serving.

#### 2.3.0-next.0

##### Minor Changes

- [`ee97130`](https://github.com/backstage/backstage/commit/ee97130): Added support for `techdocs.generator.pullOptions` when pulling the TechDocs generator Docker image from private registries that require authentication.

##### Patch Changes

- [`932986c`](https://github.com/backstage/backstage/commit/932986c): Improve validation of TechDocs static content paths.
- [`1b0e277`](https://github.com/backstage/backstage/commit/1b0e277): Improved path validation for TechDocs content serving.

### `@backstage/plugin-techdocs-react` (1.3.14 → [1.4.1-next.0](../../changelogs/@backstage/plugin-techdocs-react.md#141-next0))

#### 1.4.0

##### Minor Changes

- [`4d4f987`](https://github.com/backstage/backstage/commit/4d4f987): Add engine abstraction layer for multi-engine TechDocs support. Introduces `--engine` flag, engine config map, generator registry with `backstage.io/techdocs-engine` annotation support, `engine` field in `techdocs_metadata.json`, `serve:raw` command, and live-reload adapter interface. MkDocs remains the default with no behavior change.

  The built-in generator is now registered under `mkdocs`; the previous `techdocs` key is kept as an alias, so existing `generators.register('techdocs', ...)` calls continue to work. The CLI's `--engine` flag takes precedence over the `backstage.io/techdocs-engine` annotation for all commands, and `serve:mkdocs` and the `--mkdocs-parameter-*` flags now print deprecation warnings.

##### Patch Changes

- [`f624dc6`](https://github.com/backstage/backstage/commit/f624dc6): Fixed Material UI styles for TechDocs addons in module-federated applications.
- [`450dd64`](https://github.com/backstage/backstage/commit/450dd64): Isolated TechDocs addons in individual Suspense boundaries so that a lazy addon no longer hides the surrounding reader while it loads.
- [`7a4f545`](https://github.com/backstage/backstage/commit/7a4f545): Prevented TechDocs content from briefly appearing before page styles load.

#### 1.3.16-next.2

##### Patch Changes

- [`450dd64`](https://github.com/backstage/backstage/commit/450dd64): Isolated TechDocs addons in individual Suspense boundaries so that a lazy addon no longer hides the surrounding reader while it loads.

#### 1.3.16-next.1

##### Patch Changes

- [`f624dc6`](https://github.com/backstage/backstage/commit/f624dc6): Fixed Material UI styles for TechDocs addons in module-federated applications.
- [`7a4f545`](https://github.com/backstage/backstage/commit/7a4f545): Prevented TechDocs content from briefly appearing before page styles load.

#### 1.3.15

##### Patch Changes

- [`736d84e`](https://github.com/backstage/backstage/commit/736d84e): Use locale-insensitive Unicode casing for consistent string handling across environments.

### `@techdocs/cli` (1.11.4 → [1.14.0-next.0](../../changelogs/@techdocs/cli.md#1140-next0))

#### 1.14.0-next.0

##### Minor Changes

- [`a4604d2`](https://github.com/backstage/backstage/commit/a4604d2): Add Zensical support to `serve`, `serve:raw` and `generate` via `--engine zensical` (or the `backstage.io/techdocs-engine` annotation in `catalog-info.yaml`), including live reload in the preview app. The default `--docker-image` is now chosen per engine instead of always being `spotify/techdocs`, and matches the image the TechDocs backend uses for that engine, so MkDocs previews now use `spotify/techdocs:v1.2.8` instead of `latest`. Passing `--docker-image` explicitly behaves as before.

  The `serve` flags `--mkdocs-port`, `--mkdocs-config-file-name` and `--mkdocs-parameter-*` are deprecated in favor of `--engine-port`, `--config-file-name` and `--parameter-*`. If both the old and new flag are given, the new one wins and the warning says the old one is ignored.

#### 1.13.0

##### Minor Changes

- [`4d4f987`](https://github.com/backstage/backstage/commit/4d4f987): Add engine abstraction layer for multi-engine TechDocs support. Introduces `--engine` flag, engine config map, generator registry with `backstage.io/techdocs-engine` annotation support, `engine` field in `techdocs_metadata.json`, `serve:raw` command, and live-reload adapter interface. MkDocs remains the default with no behavior change.

  The built-in generator is now registered under `mkdocs`; the previous `techdocs` key is kept as an alias, so existing `generators.register('techdocs', ...)` calls continue to work. The CLI's `--engine` flag takes precedence over the `backstage.io/techdocs-engine` annotation for all commands, and `serve:mkdocs` and the `--mkdocs-parameter-*` flags now print deprecation warnings.

#### 1.12.0

##### Minor Changes

- [`57205a0`](https://github.com/backstage/backstage/commit/57205a0): Added a `--dangerouslyAllowAdditionalKeys` option to `techdocs-cli generate`
- [`c4976e0`](https://github.com/backstage/backstage/commit/c4976e0): The `generate` command now automatically computes a sha256 content hash of the generated site output and stores it as the etag in `techdocs_metadata.json` when no `--etag` value is explicitly provided.

  Added `--skip-if-unchanged` flag to `publish` that compares the local etag against the remote etag before uploading. When they match, the publish step is skipped entirely. This avoids redundant uploads in CI pipelines when docs haven't changed between builds.

##### Patch Changes

- [`de92fae`](https://github.com/backstage/backstage/commit/de92fae): Fixed an issue where `techdocs-cli serve` would silently stop detecting documentation changes and no longer refresh the browser when the Python environment (TechDocs container image or local) contains `click` 8.3.x. The CLI now explicitly enables MkDocs live reload when serving.
- [`4441911`](https://github.com/backstage/backstage/commit/4441911): Improved MkDocs configuration file handling.

#### 1.11.5-next.1

##### Patch Changes

- [`4441911`](https://github.com/backstage/backstage/commit/4441911): Improved MkDocs configuration file handling.

## Other patch version bumps

### `@backstage/backend-test-utils` (1.11.6 → [1.11.9-next.0](../../changelogs/@backstage/backend-test-utils.md#1119-next0))

#### 1.11.8

##### Patch Changes

- [`f6054ac`](https://github.com/backstage/backstage/commit/f6054ac): Test backends now provide the default experimental connections service for plugins and modules that declare connection dependencies.
- [`7728fcd`](https://github.com/backstage/backstage/commit/7728fcd): Improved test database cleanup reliability by shutting down independent database engines and removing their logical databases concurrently.
- [`e956084`](https://github.com/backstage/backstage/commit/e956084): Updated the root instance metadata service mock to provide an instance ID.

#### 1.11.8-next.2

##### Patch Changes

- [`f6054ac`](https://github.com/backstage/backstage/commit/f6054ac): Test backends now provide the default experimental connections service for plugins and modules that declare connection dependencies.

#### 1.11.8-next.1

##### Patch Changes

- [`e956084`](https://github.com/backstage/backstage/commit/e956084): Updated the root instance metadata service mock to provide an instance ID.

#### 1.11.8-next.0

##### Patch Changes

- [`7728fcd`](https://github.com/backstage/backstage/commit/7728fcd): Improved test database cleanup reliability by shutting down independent database engines and removing their logical databases concurrently.

#### 1.11.7

##### Patch Changes

- [`05d03ee`](https://github.com/backstage/backstage/commit/05d03ee): Increased the test database cleanup timeout to 60 seconds to reduce timeout failures when using Docker.

### `@backstage/catalog-client` (1.16.1 → [1.16.3](../../changelogs/@backstage/catalog-client.md#1163))

#### 1.16.3

##### Patch Changes

- [`6c74f3f`](https://github.com/backstage/backstage/commit/6c74f3f): Fixed the conversion of legacy filters that happens when a request has both a `filter` and a `query`, so that it matches the semantics of the legacy filter query parameter. Empty filters no longer turn into a predicate that matches nothing, empty records no longer match everything, and string values take precedence over `CATALOG_FILTER_EXISTS` for the same key.
- [`aeb9393`](https://github.com/backstage/backstage/commit/aeb9393): The `InMemoryCatalogClient` test utility now matches entities the same way as the catalog backend. Both `filter` and `query` are evaluated against the same search rows that the backend builds for its search table, instead of `query` being evaluated against raw entity JSON. This affects `getEntities`, `getEntitiesByRefs`, `queryEntities`, `streamEntities`, and `getEntityFacets`.

  This fixes several cases where the fake returned different results than a real catalog, which may change the outcome of existing tests:

  - Relation shorthand such as `{ 'relations.hasMember': 'user:default/alice' }` now works in `query`, including with `$in`, `$hasPrefix`, `$exists`, `$contains`, and logical operators.
  - Field keys are matched case-insensitively in both `filter` and `query`. For example, `{ 'spec.dependsOn': ... }` previously never matched in `filter`, and `{ 'METADATA.NAME': ... }` never matched in `query`.
  - Entities without a `metadata.namespace` now match `{ 'metadata.namespace': 'default' }` in `query`.
  - Values longer than 200 characters can no longer be matched by value, but still satisfy `$exists: true`, as in the backend.
  - `metadata.name`, `metadata.namespace`, and `metadata.uid` always satisfy `$exists: true`, even when the entity has no value for them.
  - Predicates that the backend does not support are now rejected up front with an `InputError`, even when no entities would be evaluated. For example, an object `$contains` on any field other than `relations`, or a `relations` `$contains` without a `type`.
  - Entities that have keys differing only in casing, such as `spec.foo` and `spec.Foo`, now cause an `InputError` when matched, since the backend refuses to store such entities.

- [`e844921`](https://github.com/backstage/backstage/commit/e844921): `streamEntities` no longer asks the catalog backend to compute the total number of matching items, since that count is never part of the streamed result. This also applies to the catalog service in `@backstage/plugin-catalog-node`, which delegates to the client. The `totalItems` option of `StreamEntitiesRequest` is now deprecated and ignored.

#### 1.16.2

##### Patch Changes

- [`736d84e`](https://github.com/backstage/backstage/commit/736d84e): Use locale-insensitive Unicode casing for consistent string handling across environments.

### `@backstage/catalog-model` (1.10.0 → [1.10.2](../../changelogs/@backstage/catalog-model.md#1102))

#### 1.10.2

##### Patch Changes

- [`f487744`](https://github.com/backstage/backstage/commit/f487744): Switched to version 4 of `zod` for internal validation. Error messages for invalid catalog model layer operations now use the updated `zod` wording.

  This package no longer pulls in version 3 of `zod`. If your own packages use `zod` without declaring it as a dependency, they may now get version 4 instead, so make sure to add it to their `package.json` explicitly.

#### 1.10.1

##### Patch Changes

- [`736d84e`](https://github.com/backstage/backstage/commit/736d84e): Use locale-insensitive Unicode casing for consistent string handling across environments.
- [`61809fe`](https://github.com/backstage/backstage/commit/61809fe): Allow independently registered catalog model sources to share identical layers, while reporting a clear error for conflicting layers with the same ID.
- [`78656f8`](https://github.com/backstage/backstage/commit/78656f8): Fixed several issues in the alpha catalog model layer system. Schema updates now preserve sibling field validation when changing a property named `type`, support deleting inherited fields and constraints, and retain literal JSON values in `const` and `default`. Kind schemas without an explicit root type retain their fields, and invalid combined schemas are rejected during model compilation. Empty kind descriptions and reverse relation titles are now applied correctly.

### `@backstage/config` (1.3.8 → [1.3.10](../../changelogs/@backstage/config.md#1310))

#### 1.3.10

##### Patch Changes

- [`e156078`](https://github.com/backstage/backstage/commit/e156078): Reading a number from a configuration value that is an empty or whitespace-only string now fails with a clear conversion error, instead of silently returning `0`. Numeric strings, including ones with surrounding whitespace such as `'  42  '`, continue to be parsed as expected.

#### 1.3.9

##### Patch Changes

- [`1134d4b`](https://github.com/backstage/backstage/commit/1134d4b): Fixed reading a duration from configuration so that an all-zero ISO 8601 duration (such as `PT0S`) now yields a consistent zero value instead of an empty result.

### `@backstage/config-loader` (1.11.2 → [1.11.4](../../changelogs/@backstage/config-loader.md#1114))

#### 1.11.4

##### Patch Changes

- [`e5b7381`](https://github.com/backstage/backstage/commit/e5b7381): Config schemas now compile in roughly half the time, by skipping Ajv's code optimizer. The compiled validators only run a few times per process, so the optimized code never paid for itself. This speeds up backend startup, which compiles the full config schema, for example to find the secret config values to redact from logs.

### `@backstage/core-app-api` (1.20.4 → [1.20.7-next.0](../../changelogs/@backstage/core-app-api.md#1207-next0))

#### 1.20.5

##### Patch Changes

- [`736d84e`](https://github.com/backstage/backstage/commit/736d84e): Use locale-insensitive Unicode casing for consistent string handling across environments.

### `@backstage/errors` (1.3.1 → [1.3.2](../../changelogs/@backstage/errors.md#132))

#### 1.3.2

##### Patch Changes

- [`603898f`](https://github.com/backstage/backstage/commit/603898f): Fixed `serializeError` so that stack traces are stripped from all nested error causes when stacks are not requested, not just the first-level cause.

### `@backstage/integration` (2.1.1 → [2.1.3](../../changelogs/@backstage/integration.md#213))

#### 2.1.3

##### Patch Changes

- [`1f603db`](https://github.com/backstage/backstage/commit/1f603db): Azure DevOps repository files now resolve to an edit URL when used by integrations such as TechDocs.
- [`7d17e72`](https://github.com/backstage/backstage/commit/7d17e72): Fixed Azure DevOps file and archive downloads to use the requested branch or tag, including when checking whether a repository tree has changed. Branches and tags with the same name are now distinguished.
- [`4bd3c42`](https://github.com/backstage/backstage/commit/4bd3c42): Bitbucket Cloud OAuth access tokens returned by `getBitbucketCloudOAuthToken` are now cached separately for each set of OAuth client credentials. Previously a single token was cached globally, which could cause the wrong token to be used when more than one Bitbucket Cloud integration was configured or when OAuth credentials were rotated.
- [`933e50e`](https://github.com/backstage/backstage/commit/933e50e): Fixed importing this package from ECMAScript module (ESM) projects, which failed since 2.1.0 with an error saying that `lodash` does not provide an export named `trimEnd`.
- [`0c9d72c`](https://github.com/backstage/backstage/commit/0c9d72c): Update Bitbucket Cloud Authentication logic to support bearer API token

#### 2.1.2

##### Patch Changes

- [`23705f3`](https://github.com/backstage/backstage/commit/23705f3): Fixed an issue where reading or downloading files from Bitbucket Server could fail when the branch name contained special characters such as an ampersand or a plus sign. The branch name is now correctly encoded in the request URL.
- [`736d84e`](https://github.com/backstage/backstage/commit/736d84e): Use locale-insensitive Unicode casing for consistent string handling across environments.
- [`7150117`](https://github.com/backstage/backstage/commit/7150117): Updated internal Azure DevOps imports to avoid a circular module dependency.
- [`e592bc5`](https://github.com/backstage/backstage/commit/e592bc5): Fixed an issue where reading files from GitLab could fail when the branch name contained special characters such as an ampersand or a plus sign. The branch name is now correctly encoded in the request URL.
- [`e895def`](https://github.com/backstage/backstage/commit/e895def): Fixed handling of GitLab URLs for instances configured with a relative base path.

### `@backstage/plugin-catalog` (2.0.8 → [2.0.11-next.0](../../changelogs/@backstage/plugin-catalog.md#2011-next0))

#### 2.0.10

##### Patch Changes

- [`6c74f3f`](https://github.com/backstage/backstage/commit/6c74f3f): The catalog export button now respects filters that implement `getCatalogQuery`.
- [`13adaa1`](https://github.com/backstage/backstage/commit/13adaa1): Updated internal React component names to improve debugging and tooling compatibility.
- [`a7a1274`](https://github.com/backstage/backstage/commit/a7a1274): Use EntityDisplayName for hierarchy links in BUI entity header in order to display titles

#### 2.0.10-next.3

##### Patch Changes

- [`6c74f3f`](https://github.com/backstage/backstage/commit/6c74f3f): The catalog export button now respects filters that implement `getCatalogQuery`.

#### 2.0.10-next.1

##### Patch Changes

- [`13adaa1`](https://github.com/backstage/backstage/commit/13adaa1): Updated internal React component names to improve debugging and tooling compatibility.
- [`a7a1274`](https://github.com/backstage/backstage/commit/a7a1274): Use EntityDisplayName for hierarchy links in BUI entity header in order to display titles

#### 2.0.9

##### Patch Changes

- [`8e0e3c4`](https://github.com/backstage/backstage/commit/8e0e3c4): Fixed a regression where the About card's field labels (OWNER, SYSTEM, TAGS, etc.) lost their vertical gap above the value.
- [`e3781a3`](https://github.com/backstage/backstage/commit/e3781a3): Fixed circular dependency warnings when building the catalog plugin.
- [`d9a949e`](https://github.com/backstage/backstage/commit/d9a949e): Fixed the About card to safely show and hide filtered icon links when navigating between entities, without initializing hidden links.
- [`736d84e`](https://github.com/backstage/backstage/commit/736d84e): Use locale-insensitive Unicode casing for consistent string handling across environments.
- [`4611178`](https://github.com/backstage/backstage/commit/4611178): Add support for legacy props in catalog entity card exports by widening the public TypeScript prop types. This ensures compatibility for consumers still using legacy properties such as `variant` and `columns`.
- [`d421187`](https://github.com/backstage/backstage/commit/d421187): Reduced the initial app bundle size by loading page and optional UI implementations only when their extensions render.
- [`acc6666`](https://github.com/backstage/backstage/commit/acc6666): Fixed entity context menus to report errors from contributed items without disrupting the menu.

#### 2.0.9-next.2

##### Patch Changes

- [`4611178`](https://github.com/backstage/backstage/commit/4611178): Add support for legacy props in catalog entity card exports by widening the public TypeScript prop types. This ensures compatibility for consumers still using legacy properties such as `variant` and `columns`.
- [`acc6666`](https://github.com/backstage/backstage/commit/acc6666): Fixed entity context menus to report errors from contributed items without disrupting the menu.

#### 2.0.9-next.1

##### Patch Changes

- [`e3781a3`](https://github.com/backstage/backstage/commit/e3781a3): Fixed circular dependency warnings when building the catalog plugin.
- [`d421187`](https://github.com/backstage/backstage/commit/d421187): Reduced the initial app bundle size by loading page and optional UI implementations only when their extensions render.

### `@backstage/plugin-search` (1.7.7 → [1.7.10-next.0](../../changelogs/@backstage/plugin-search.md#1710-next0))

#### 1.7.8

##### Patch Changes

- [`d421187`](https://github.com/backstage/backstage/commit/d421187): Reduced the initial app bundle size by loading page and optional UI implementations only when their extensions render.

#### 1.7.8-next.1

##### Patch Changes

- [`d421187`](https://github.com/backstage/backstage/commit/d421187): Reduced the initial app bundle size by loading page and optional UI implementations only when their extensions render.

### `@backstage/plugin-search-backend` (2.1.6 → [2.1.9-next.0](../../changelogs/@backstage/plugin-search-backend.md#219-next0))

#### 2.1.7

##### Patch Changes

- [`b11c9b4`](https://github.com/backstage/backstage/commit/b11c9b4): Fixed a bug where the search engine could receive an unfiltered query when no document types were permitted.

#### 2.1.7-next.0

##### Patch Changes

- [`b11c9b4`](https://github.com/backstage/backstage/commit/b11c9b4): Fixed a bug where the search engine could receive an unfiltered query when no document types were permitted.

### `@backstage/plugin-search-backend-node` (1.4.7 → [1.4.10-next.0](../../changelogs/@backstage/plugin-search-backend-node.md#1410-next0))

#### 1.4.8

##### Patch Changes

- [`736d84e`](https://github.com/backstage/backstage/commit/736d84e): Use locale-insensitive Unicode casing for consistent string handling across environments.

### `@backstage/plugin-techdocs-addons-test-utils` (2.0.8 → [2.0.11-next.0](../../changelogs/@backstage/plugin-techdocs-addons-test-utils.md#2011-next0))

#### 2.0.9

##### Patch Changes

- [`279fdf6`](https://github.com/backstage/backstage/commit/279fdf6): Declared the DOM Testing Library dependency required by React Testing Library.

#### 2.0.9-next.1

##### Patch Changes

- [`279fdf6`](https://github.com/backstage/backstage/commit/279fdf6): Declared the DOM Testing Library dependency required by React Testing Library.

### `@backstage/plugin-techdocs-module-addons-contrib` (1.1.39 → [1.1.42-next.0](../../changelogs/@backstage/plugin-techdocs-module-addons-contrib.md#1142-next0))

#### 1.1.40

##### Patch Changes

- [`736d84e`](https://github.com/backstage/backstage/commit/736d84e): Use locale-insensitive Unicode casing for consistent string handling across environments.
- [`10d2720`](https://github.com/backstage/backstage/commit/10d2720): Keep the TechDocs LightBox addon's image viewer out of an app's initial bundle by loading it with the first documentation page.

### `@backstage/test-utils` (1.7.21 → [1.7.24-next.0](../../changelogs/@backstage/test-utils.md#1724-next0))

#### 1.7.22

##### Patch Changes

- [`279fdf6`](https://github.com/backstage/backstage/commit/279fdf6): Declared the DOM Testing Library dependency required by React Testing Library.

#### 1.7.22-next.1

##### Patch Changes

- [`279fdf6`](https://github.com/backstage/backstage/commit/279fdf6): Declared the DOM Testing Library dependency required by React Testing Library.

## Excluded dependency updates

- `@backstage/app-defaults` (1.7.11 → [1.7.14-next.0](../../changelogs/@backstage/app-defaults.md#1714-next0))
- `@backstage/cli-module-config` (0.1.6 → [0.1.9-next.0](../../changelogs/@backstage/cli-module-config.md#019-next0))
- `@backstage/cli-module-github` (0.1.4 → [0.1.6-next.0](../../changelogs/@backstage/cli-module-github.md#016-next0))
- `@backstage/cli-module-info` (0.1.4 → [0.1.6-next.0](../../changelogs/@backstage/cli-module-info.md#016-next0))
- `@backstage/cli-module-lint` (0.1.5 → [0.1.7-next.0](../../changelogs/@backstage/cli-module-lint.md#017-next0))
- `@backstage/cli-module-migrate` (0.2.1 → [0.2.3-next.0](../../changelogs/@backstage/cli-module-migrate.md#023-next0))
- `@backstage/cli-module-translations` (0.1.4 → [0.1.6-next.0](../../changelogs/@backstage/cli-module-translations.md#016-next0))
- `@backstage/core-plugin-api` (1.12.9 → [1.12.12-next.0](../../changelogs/@backstage/core-plugin-api.md#11212-next0))
- `@backstage/dev-utils` (1.1.26 → [1.1.29-next.0](../../changelogs/@backstage/dev-utils.md#1129-next0))
- `@backstage/frontend-defaults` (0.5.5 → [0.5.8-next.0](../../changelogs/@backstage/frontend-defaults.md#058-next0))
- `@backstage/frontend-dev-utils` (0.1.5 → [0.1.8-next.0](../../changelogs/@backstage/frontend-dev-utils.md#018-next0))
- `@backstage/integration-aws-node` (0.2.1 → [0.2.3](../../changelogs/@backstage/integration-aws-node.md#023))
- `@backstage/integration-react` (1.2.21 → [1.2.24-next.0](../../changelogs/@backstage/integration-react.md#1224-next0))
- `@backstage/plugin-app-node` (0.1.48 → [0.1.51-next.0](../../changelogs/@backstage/plugin-app-node.md#0151-next0))
- `@backstage/plugin-auth` (0.1.11 → [0.1.14-next.0](../../changelogs/@backstage/plugin-auth.md#0114-next0))
- `@backstage/plugin-auth-backend-module-bitbucket-provider` (0.3.18 → [0.3.21-next.0](../../changelogs/@backstage/plugin-auth-backend-module-bitbucket-provider.md#0321-next0))
- `@backstage/plugin-auth-backend-module-bitbucket-server-provider` (0.2.18 → [0.2.21-next.0](../../changelogs/@backstage/plugin-auth-backend-module-bitbucket-server-provider.md#0221-next0))
- `@backstage/plugin-auth-backend-module-gitlab-provider` (0.4.6 → [0.4.9-next.0](../../changelogs/@backstage/plugin-auth-backend-module-gitlab-provider.md#049-next0))
- `@backstage/plugin-auth-backend-module-google-provider` (0.3.18 → [0.3.21-next.0](../../changelogs/@backstage/plugin-auth-backend-module-google-provider.md#0321-next0))
- `@backstage/plugin-auth-backend-module-oauth2-provider` (0.4.18 → [0.4.21-next.0](../../changelogs/@backstage/plugin-auth-backend-module-oauth2-provider.md#0421-next0))
- `@backstage/plugin-auth-backend-module-okta-provider` (0.2.18 → [0.2.21-next.0](../../changelogs/@backstage/plugin-auth-backend-module-okta-provider.md#0221-next0))
- `@backstage/plugin-auth-backend-module-onelogin-provider` (0.3.18 → [0.3.21-next.0](../../changelogs/@backstage/plugin-auth-backend-module-onelogin-provider.md#0321-next0))
- `@backstage/plugin-auth-backend-module-openshift-provider` (0.1.10 → [0.1.13-next.0](../../changelogs/@backstage/plugin-auth-backend-module-openshift-provider.md#0113-next0))
- `@backstage/plugin-auth-react` (0.1.30 → [0.1.33-next.0](../../changelogs/@backstage/plugin-auth-react.md#0133-next0))
- `@backstage/plugin-catalog-backend-module-ai-model` (0.1.3 → [0.1.6-next.0](../../changelogs/@backstage/plugin-catalog-backend-module-ai-model.md#016-next0))
- `@backstage/plugin-catalog-backend-module-backstage-openapi` (0.5.17 → [0.5.20-next.0](../../changelogs/@backstage/plugin-catalog-backend-module-backstage-openapi.md#0520-next0))
- `@backstage/plugin-catalog-backend-module-bitbucket-cloud` (0.5.14 → [0.5.17-next.0](../../changelogs/@backstage/plugin-catalog-backend-module-bitbucket-cloud.md#0517-next0))
- `@backstage/plugin-catalog-backend-module-gcp` (0.3.22 → [0.3.25-next.0](../../changelogs/@backstage/plugin-catalog-backend-module-gcp.md#0325-next0))
- `@backstage/plugin-catalog-backend-module-gerrit` (0.3.17 → [0.3.20-next.0](../../changelogs/@backstage/plugin-catalog-backend-module-gerrit.md#0320-next0))
- `@backstage/plugin-catalog-backend-module-github-org` (0.3.25 → [0.3.28-next.0](../../changelogs/@backstage/plugin-catalog-backend-module-github-org.md#0328-next0))
- `@backstage/plugin-catalog-backend-module-gitlab-org` (0.2.24 → [0.2.27-next.0](../../changelogs/@backstage/plugin-catalog-backend-module-gitlab-org.md#0227-next0))
- `@backstage/plugin-catalog-backend-module-logs` (0.1.25 → [0.1.28-next.0](../../changelogs/@backstage/plugin-catalog-backend-module-logs.md#0128-next0))
- `@backstage/plugin-catalog-backend-module-msgraph-incremental` (0.1.3 → [0.1.6-next.0](../../changelogs/@backstage/plugin-catalog-backend-module-msgraph-incremental.md#016-next0))
- `@backstage/plugin-catalog-backend-module-openapi` (0.2.25 → [0.2.28-next.0](../../changelogs/@backstage/plugin-catalog-backend-module-openapi.md#0228-next0))
- `@backstage/plugin-catalog-backend-module-scaffolder-entity-model` (0.2.23 → [0.2.26-next.0](../../changelogs/@backstage/plugin-catalog-backend-module-scaffolder-entity-model.md#0226-next0))
- `@backstage/plugin-catalog-node` (2.2.4 → [2.2.7-next.0](../../changelogs/@backstage/plugin-catalog-node.md#227-next0))
- `@backstage/plugin-catalog-unprocessed-entities-common` (0.0.16 → [0.0.18](../../changelogs/@backstage/plugin-catalog-unprocessed-entities-common.md#0018))
- `@backstage/plugin-config-schema` (0.1.83 → [0.1.86-next.0](../../changelogs/@backstage/plugin-config-schema.md#0186-next0))
- `@backstage/plugin-devtools-backend` (0.5.20 → [0.5.23-next.0](../../changelogs/@backstage/plugin-devtools-backend.md#0523-next0))
- `@backstage/plugin-devtools-common` (0.1.25 → [0.1.27](../../changelogs/@backstage/plugin-devtools-common.md#0127))
- `@backstage/plugin-devtools-react` (0.2.5 → [0.2.8-next.0](../../changelogs/@backstage/plugin-devtools-react.md#028-next0))
- `@backstage/plugin-events-backend-module-aws-sqs` (0.4.25 → [0.4.28-next.0](../../changelogs/@backstage/plugin-events-backend-module-aws-sqs.md#0428-next0))
- `@backstage/plugin-events-backend-module-azure` (0.2.34 → [0.2.37-next.0](../../changelogs/@backstage/plugin-events-backend-module-azure.md#0237-next0))
- `@backstage/plugin-events-backend-module-bitbucket-cloud` (0.2.34 → [0.2.37-next.0](../../changelogs/@backstage/plugin-events-backend-module-bitbucket-cloud.md#0237-next0))
- `@backstage/plugin-events-backend-module-bitbucket-server` (0.1.15 → [0.1.18-next.0](../../changelogs/@backstage/plugin-events-backend-module-bitbucket-server.md#0118-next0))
- `@backstage/plugin-events-backend-module-gerrit` (0.2.34 → [0.2.37-next.0](../../changelogs/@backstage/plugin-events-backend-module-gerrit.md#0237-next0))
- `@backstage/plugin-events-backend-module-github` (0.4.15 → [0.4.18-next.0](../../changelogs/@backstage/plugin-events-backend-module-github.md#0418-next0))
- `@backstage/plugin-events-backend-module-gitlab` (0.3.15 → [0.3.18-next.0](../../changelogs/@backstage/plugin-events-backend-module-gitlab.md#0318-next0))
- `@backstage/plugin-events-backend-module-google-pubsub` (0.2.6 → [0.2.9-next.0](../../changelogs/@backstage/plugin-events-backend-module-google-pubsub.md#029-next0))
- `@backstage/plugin-events-backend-module-kafka` (0.3.7 → [0.3.10-next.0](../../changelogs/@backstage/plugin-events-backend-module-kafka.md#0310-next0))
- `@backstage/plugin-events-backend-test-utils` (0.1.58 → [0.1.61-next.0](../../changelogs/@backstage/plugin-events-backend-test-utils.md#0161-next0))
- `@backstage/plugin-events-node` (0.4.25 → [0.4.28-next.0](../../changelogs/@backstage/plugin-events-node.md#0428-next0))
- `@backstage/plugin-gateway-backend` (1.1.8 → [1.1.11-next.0](../../changelogs/@backstage/plugin-gateway-backend.md#1111-next0))
- `@backstage/plugin-notifications-common` (0.2.3 → [0.2.5](../../changelogs/@backstage/plugin-notifications-common.md#025))
- `@backstage/plugin-org-react` (0.1.53 → [0.1.56-next.0](../../changelogs/@backstage/plugin-org-react.md#0156-next0))
- `@backstage/plugin-permission-backend` (0.7.15 → [0.7.18-next.0](../../changelogs/@backstage/plugin-permission-backend.md#0718-next0))
- `@backstage/plugin-permission-backend-module-allow-all-policy` (0.2.22 → [0.2.25-next.0](../../changelogs/@backstage/plugin-permission-backend-module-allow-all-policy.md#0225-next0))
- `@backstage/plugin-permission-common` (0.9.10 → [0.9.12](../../changelogs/@backstage/plugin-permission-common.md#0912))
- `@backstage/plugin-permission-node` (0.11.3 → [0.11.6-next.0](../../changelogs/@backstage/plugin-permission-node.md#0116-next0))
- `@backstage/plugin-permission-react` (0.5.4 → [0.5.7-next.0](../../changelogs/@backstage/plugin-permission-react.md#057-next0))
- `@backstage/plugin-proxy-node` (0.1.18 → [0.1.21-next.0](../../changelogs/@backstage/plugin-proxy-node.md#0121-next0))
- `@backstage/plugin-scaffolder-backend-module-cookiecutter` (0.3.26 → [0.3.29-next.0](../../changelogs/@backstage/plugin-scaffolder-backend-module-cookiecutter.md#0329-next0))
- `@backstage/plugin-scaffolder-backend-module-gerrit` (0.2.24 → [0.2.27-next.0](../../changelogs/@backstage/plugin-scaffolder-backend-module-gerrit.md#0227-next0))
- `@backstage/plugin-scaffolder-backend-module-gitea` (0.2.24 → [0.2.27-next.0](../../changelogs/@backstage/plugin-scaffolder-backend-module-gitea.md#0227-next0))
- `@backstage/plugin-scaffolder-backend-module-notifications` (0.1.25 → [0.1.28-next.0](../../changelogs/@backstage/plugin-scaffolder-backend-module-notifications.md#0128-next0))
- `@backstage/plugin-scaffolder-backend-module-rails` (0.5.24 → [0.5.27-next.0](../../changelogs/@backstage/plugin-scaffolder-backend-module-rails.md#0527-next0))
- `@backstage/plugin-scaffolder-backend-module-yeoman` (0.4.25 → [0.4.28-next.0](../../changelogs/@backstage/plugin-scaffolder-backend-module-yeoman.md#0428-next0))
- `@backstage/plugin-scaffolder-node-test-utils` (0.3.14 → [0.3.17-next.0](../../changelogs/@backstage/plugin-scaffolder-node-test-utils.md#0317-next0))
- `@backstage/plugin-search-backend-module-stack-overflow-collator` (0.3.23 → [0.3.26-next.0](../../changelogs/@backstage/plugin-search-backend-module-stack-overflow-collator.md#0326-next0))
- `@backstage/plugin-search-common` (1.2.24 → [1.2.26](../../changelogs/@backstage/plugin-search-common.md#1226))
- `@backstage/plugin-search-react` (1.11.7 → [1.11.10-next.0](../../changelogs/@backstage/plugin-search-react.md#11110-next0))
- `@backstage/plugin-signals-node` (0.2.4 → [0.2.7-next.0](../../changelogs/@backstage/plugin-signals-node.md#027-next0))
- `@backstage/plugin-signals-react` (0.0.25 → [0.0.28-next.0](../../changelogs/@backstage/plugin-signals-react.md#0028-next0))
- `@backstage/plugin-user-settings-backend` (0.4.6 → [0.4.9-next.0](../../changelogs/@backstage/plugin-user-settings-backend.md#049-next0))
