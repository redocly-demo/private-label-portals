# Private label demo of Redocly Developer portal

## Prerequisites

- [node.js >= 12.4.0](https://nodejs.org/en/)
- [yarn](https://yarnpkg.com/en/)

## Install

    yarn install

## Start development server

    yarn start

Note: search isn't functional in the development environment.

## Troubleshooting

We heavily rely on caching for performance issues so if some changes are not reflected in the resulting portal try cleaning cache by running:

    yarn clean

## Docs

Read the [online documentation](https://redoc.ly/docs/developer-portal/introduction/).

## Environments for each materialized portal

We'll make 3 private label portals:

- rock
- paper
- scissors

We'll use [environment variable files](https://redoc.ly/docs/developer-portal/environment-variables/) to do this by adding these files:

- env.rock
- env.paper
- env.scissors

> Override which environment file is used by setting an environment variable named `REDOCLY_ACTIVE_ENV`.

### Variables

To simplify this private label demo, we'll set three variables:

- LOGO
- NAME
- PRIMARY_COLOR

There is no restriction on the number of variables you set (but there is some restriction in the naming, such as don't start them with `REDOCLY_`).

### Usage of env variables

In yaml:

- `{{process.env.MY_TITLE}}`

In md (and md portion of mdx pages):

- `{{process.env.MY_TITLE}}`

In js (and jsx portions of mdx pages):

-  `<H1>Heading In Here Big Text {process.env.WELCOME_MESSAGE}</H1>`

In ts (e.g. in theme.ts):

- `process.env.MY_TITLE`
