![license](https://img.shields.io/badge/License-Apache%202.0-blue?logo=apache&style=flat-square)
[![npm](https://img.shields.io/npm/v/@dust-defi/api?logo=npm&style=flat-square)](https://www.npmjs.com/package/@dust-defi/api)

# @dust-defi

This library provides additional typing information for user to access Dust Chain by using [polkadot.js](https://github.com/polkadot-js/api).

# Getting Started

More documentation and examples on [wiki](https://docs.dust.llc/).

- Install dependencies

```bash
yarn add @polkadot/api @dust-defi/api@beta
```

- Create API instance

```ts
import { ApiPromise } from '@polkadot/api';
import { WsProvider } from '@polkadot/rpc-provider';
import { options } from '@dust-defi/api';

async function main() {
    const provider = new WsProvider('wss://rpc-testnet-scan.dust.llc/ws');
    const api = new ApiPromise(options({ provider }));
    await api.isReady;

    // use api
}

main()
```

- Use api to interact with node

```ts
// query and display account data
const data = await api.query.system.account('5F98oWfz2r5rcRVnP9VCndg33DAAsky3iuoBSpaPUbgN9AJn');
console.log(data.toHuman())
```

# Packages

- [api](./packages/api)
  - Contains necessary options to create a polkadot.js API instance
- [api-derive](./packages/api-derive)
  - Additional polkadot.js derives for Dust Chain
- [app-util](./packages/app-util)
  - Utilities to work with Dust Chain
- [types](./packages/types)
  - Polkadot.js type definations for Dust Chain
