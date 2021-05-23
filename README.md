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

Create three portals that connect to the same repository:

![three-portals](https://user-images.githubusercontent.com/1161871/119276237-66b26300-bbdf-11eb-8f06-2831e40e85c5.png)

> Override which environment file is used by setting an environment variable named `REDOCLY_ACTIVE_ENV`.

Set the `REDOCLY_ACTIVE_ENV` value inside of the portal's **Settings > Environment variables**:

![image](https://user-images.githubusercontent.com/1161871/119276141-c78d6b80-bbde-11eb-8c3d-31f7db82446b.png)

### Variables

To simplify this private label demo, we'll set three variables:

- LOGO
- NAME
- PRIMARY_COLOR

See the `.env.rock` file for example. There is no restriction on the number of variables you set (but there is some restriction in the naming, such as don't start them with `REDOCLY_`).

```
LOGO=images/rock.png
PRIMARY_COLOR=blue
NAME=Rock
```

### Usage of env variables

In yaml:

- `{{process.env.MY_TITLE}}`

In md (and md portion of mdx pages):

- `{{process.env.MY_TITLE}}`

In js (and jsx portions of mdx pages):

-  `<H1>Heading In Here Big Text {process.env.WELCOME_MESSAGE}</H1>`

In ts (e.g. in theme.ts):

- `process.env.MY_TITLE`

### Results

See the three portals:

- https://private-label-demo-rock.redoc.ly/
- https://private-label-demo-paper.redoc.ly/
- https://private-label-demo-scissors.redoc.ly/

(They could be set up with completely different custom domains.)
