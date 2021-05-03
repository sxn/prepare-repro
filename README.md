# Reproduction case for [prepare script not running](https://github.com/npm/cli/issues/2890)

## GitHub dependency

```sh
~/P/p/github (main)> rm -rf node_modules/
~/P/p/github (main)> rm package-lock.json
~/P/p/github (main)> npm --version
7.11.2
~/P/p/github (main)> npm install
npm WARN deprecated @hapi/topo@3.1.6: This version has been deprecated and is no longer supported or maintained
npm WARN deprecated @hapi/bourne@1.3.2: This version has been deprecated and is no longer supported or maintained
npm WARN deprecated urix@0.1.0: Please see https://github.com/lydell/urix#deprecated
npm WARN deprecated eslint-loader@2.2.1: This loader has been deprecated. Please use eslint-webpack-plugin
npm WARN deprecated resolve-url@0.2.1: https://github.com/lydell/resolve-url#deprecated
npm WARN deprecated chokidar@2.1.8: Chokidar 2 will break on node v14+. Upgrade to chokidar 3 with 15x less dependencies.
npm WARN deprecated fsevents@1.2.13: fsevents 1 will break on node v14+ and could be using insecure binaries. Upgrade to fsevents 2.
npm WARN deprecated fsevents@1.2.13: fsevents 1 will break on node v14+ and could be using insecure binaries. Upgrade to fsevents 2.
npm WARN deprecated chokidar@2.1.8: Chokidar 2 will break on node v14+. Upgrade to chokidar 3 with 15x less dependencies.
npm WARN deprecated babel-eslint@10.1.0: babel-eslint is now @babel/eslint-parser. This package will no longer receive updates.
npm WARN deprecated @hapi/address@2.1.4: Moved to 'npm install @sideway/address'
npm WARN deprecated @hapi/hoek@8.5.1: This version has been deprecated and is no longer supported or maintained
npm WARN deprecated @hapi/joi@15.1.1: Switch to 'npm install joi'

added 2061 packages, and audited 2062 packages in 1m

171 packages are looking for funding
  run `npm fund` for details

5 moderate severity vulnerabilities

To address all issues, run:
  npm audit fix

Run `npm audit` for details.
~/P/p/github (main)> ls node_modules/gatsby-plugin-advanced-sitemap/
BaseSiteMapGenerator.js README.md               defaults.js             index.js                jest.setup.js           renovate.json           utils.js
IndexMapGenerator.js    SiteMapGenerator.js     gatsby-node.js          jest-transformer.js     node_modules            src
LICENSE                 SiteMapManager.js       gatsby-ssr.js           jest.config.js          package.json            static
```

Notably, the following files have been generated:

- `BaseSitemapGenerator.js`
- `IndexMapGenerator.js`
- `SiteMapGenerator.js`
- `SiteMapManager.js`
- `defaults.js`
- `gatsby-node.js`
- `gatsby-ssr.js`
- `utils.js`

## Tarball dependency

```sh
~/P/p/tarball (main)> rm -rf node_modules/
~/P/p/tarball (main)> rm package-lock.json
~/P/p/tarball (main)> npm --version
7.11.2
~/P/p/tarball (main)> npm install
npm WARN deprecated @hapi/bourne@1.3.2: This version has been deprecated and is no longer supported or maintained
npm WARN deprecated @hapi/topo@3.1.6: This version has been deprecated and is no longer supported or maintained
npm WARN deprecated urix@0.1.0: Please see https://github.com/lydell/urix#deprecated
npm WARN deprecated eslint-loader@2.2.1: This loader has been deprecated. Please use eslint-webpack-plugin
npm WARN deprecated resolve-url@0.2.1: https://github.com/lydell/resolve-url#deprecated
npm WARN deprecated chokidar@2.1.8: Chokidar 2 will break on node v14+. Upgrade to chokidar 3 with 15x less dependencies.
npm WARN deprecated fsevents@1.2.13: fsevents 1 will break on node v14+ and could be using insecure binaries. Upgrade to fsevents 2.
npm WARN deprecated fsevents@1.2.13: fsevents 1 will break on node v14+ and could be using insecure binaries. Upgrade to fsevents 2.
npm WARN deprecated chokidar@2.1.8: Chokidar 2 will break on node v14+. Upgrade to chokidar 3 with 15x less dependencies.
npm WARN deprecated babel-eslint@10.1.0: babel-eslint is now @babel/eslint-parser. This package will no longer receive updates.
npm WARN deprecated @hapi/address@2.1.4: Moved to 'npm install @sideway/address'
npm WARN deprecated @hapi/hoek@8.5.1: This version has been deprecated and is no longer supported or maintained
npm WARN deprecated @hapi/joi@15.1.1: Switch to 'npm install joi'

added 2061 packages, and audited 2062 packages in 36s

171 packages are looking for funding
  run `npm fund` for details

5 moderate severity vulnerabilities

To address all issues, run:
  npm audit fix

Run `npm audit` for details.
~/P/p/tarball (main)> ls node_modules/gatsby-plugin-advanced-sitemap/
LICENSE             index.js            jest.config.js      node_modules        renovate.json       static
README.md           jest-transformer.js jest.setup.js       package.json        src                 yarn.lock
```

Notably, the following files are missing:

- `BaseSitemapGenerator.js`
- `IndexMapGenerator.js`
- `SiteMapGenerator.js`
- `SiteMapManager.js`
- `defaults.js`
- `gatsby-node.js`
- `gatsby-ssr.js`
- `utils.js`
