# Serverless Framework Monorepo

Example monorepo with multiple Serverless Framework stacks.

## Structure

The project is managed with `yarn` and `lerna`.

The `services` directory contains several Serverless Framework stacks.
Dependencies between stacks are maintained with `lerna` through
the package dependencies in the `package.json` files.

Dependencies:

```
common
`- first
|  `- second
`- third
```

Stacks are deployed in parallel, maintaining the dependencies order.

To minimize the number of created S3 buckets,
all services use the same deployment bucket from the `common` service.

## Development

Install:

```bash
yarn install
```

Deploy:

```bash
yarn run deploy
```

To deploy individual service, run `yarn run deploy` from its directory.

Remove:

```
yarn run remove
```
