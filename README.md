# Ioc Transformer
> Typescript transformer to transform import statements to IoC container use calls

[![circleci-image]][circleci-url] [![npm-image]][npm-url] ![][typescript-image] [![license-image]][license-url]

The [Ioc container](https://github.com/adonisjs/fold) of AdonisJs exposes the `use` method to resolve dependencies from the container. However, using `use` and `import` statements together feels a bit cluttered. This module enables using `import` statements for IoC container bindings and transforms them to the `use` call by hooking into the Typescript compiler lifecycle.

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
## Table of contents

- [Usage](#usage)
- [Maintainers](#maintainers)
- [Authors & License](#authors--license)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## Usage
Install the package from npm registry as follows:

```sh
npm i @adonisjs/ioc-transformer
```

Pass it to the Typescript compiler as `after` hook. Following is an example of using it with `ts-node`.

```ts
const { iocTransformer } = require('@adonisjs/ioc-transformer')

require('ts-node').register({
  transformers: {
    after: [iocTransformer(require('typescript/lib/typescript'), require('./.adonisrc.json'))],
  }
})
```

## Maintainers
[Harminder virk](https://github.com/thetutlage)

## Authors & License
[Harminder virk](https://github.com/Harminder virk) and [contributors](https://github.com/adonisjs/ioc-transformer/graphs/contributors).

MIT License, see the included [MIT](LICENSE.md) file.

[circleci-image]: https://img.shields.io/circleci/project/github/adonisjs/ioc-transformer/master.svg?style=for-the-badge&logo=circleci
[circleci-url]: https://circleci.com/gh/adonisjs/ioc-transformer "circleci"

[npm-image]: https://img.shields.io/npm/v/@adonisjs/ioc-transformer.svg?style=for-the-badge&logo=npm
[npm-url]: https://npmjs.org/package/@adonisjs/ioc-transformer "npm"

[typescript-image]: https://img.shields.io/badge/Typescript-294E80.svg?style=for-the-badge&logo=typescript

[license-url]: LICENSE.md
[license-image]: https://img.shields.io/aur/license/pac.svg?style=for-the-badge
