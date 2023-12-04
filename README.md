# TodoFrontendApp

TodoFrontendApp is a Vue.js application for managing and interacting with the TodoBackendApp API. This frontend application provides a user-friendly interface to view, add, update, and delete Todo items.

## Table of Contents
- [Introduction](#introduction)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Usage](#usage)
- [Scripts](#scripts)
- [Dependencies](#dependencies)
- [Dev Dependencies](#dev-dependencies)
- [Testing](#testing)
- [Contributing](#contributing)
- [License](#license)

## Introduction

The TodoFrontendApp is built using Nuxt.js, a progressive Vue.js framework. It leverages Bootstrap for styling and BootstrapVue for Vue.js integration with Bootstrap components.

## Prerequisites

Before running the TodoFrontendApp, ensure that you have the following prerequisites installed:

- Node.js (version 14 or later)
- Npm (Node Package Manager)
- Yarn

## Installation

1. Clone the repository:

    ```bash
    git clone https://github.com/your-username/TodoFrontendApp.git
    ```

2. Navigate to the project directory:

    ```bash
    cd TodoFrontendApp
    ```

## Build Setup

```bash
# install dependencies
$ yarn install

# serve with hot reload at localhost:3000
$ yarn dev

# build for production and launch server
$ yarn build
$ yarn start

# generate static project
$ yarn generate
```

For detailed explanation on how things work, check out the [documentation](https://nuxtjs.org).


## Scripts

- **dev**: Run the development server.
- **build**: Build the application for production.
- **start**: Start the production server.
- **generate**: Generate static files for deployment.
- **test**: Run Jest tests.

## Dependencies

- **Bootstrap**: A popular CSS framework for building responsive and mobile-first websites.
- **BootstrapVue**: Bootstrap components for Vue.js.
- **Core-js**: A modular standard library for JavaScript.
- **Nuxt.js**: A progressive Vue.js framework for building modern web applications.
- **Vue.js**: A JavaScript framework for building user interfaces.
- **Vue Server Renderer**: Vue.js server-side rendering support.
- **Vue Template Compiler**: Compiler for Vue.js templates.

## Dev Dependencies

- **@nuxt/types**: Nuxt.js types.
- **@nuxt/typescript-build**: TypeScript build support for Nuxt.js.
- **@vue/test-utils**: Vue.js testing utilities.
- **Babel Core**: Babel compiler core.
- **Babel Jest**: Jest integration for Babel.
- **Jest**: A JavaScript testing framework.
- **Jest Environment Jsdom**: Jest environment for jsdom.
- **ts-jest**: TypeScript preprocessor for Jest.
- **Vue Jest**: Jest integration for Vue.js.

## Testing

The project includes Jest tests to ensure the reliability of components. Run the tests using:

```bash
yarn run test
```

## Special Directories

You can create the following extra directories, some of which have special behaviors. Only `pages` is required; you can delete them if you don't want to use their functionality.

### `assets`

The assets directory contains your uncompiled assets such as Stylus or Sass files, images, or fonts.

More information about the usage of this directory in [the documentation](https://nuxtjs.org/docs/2.x/directory-structure/assets).

### `components`

The components directory contains your Vue.js components. Components make up the different parts of your page and can be reused and imported into your pages, layouts and even other components.

More information about the usage of this directory in [the documentation](https://nuxtjs.org/docs/2.x/directory-structure/components).

### `layouts`

Layouts are a great help when you want to change the look and feel of your Nuxt app, whether you want to include a sidebar or have distinct layouts for mobile and desktop.

More information about the usage of this directory in [the documentation](https://nuxtjs.org/docs/2.x/directory-structure/layouts).


### `pages`

This directory contains your application views and routes. Nuxt will read all the `*.vue` files inside this directory and setup Vue Router automatically.

More information about the usage of this directory in [the documentation](https://nuxtjs.org/docs/2.x/get-started/routing).

### `plugins`

The plugins directory contains JavaScript plugins that you want to run before instantiating the root Vue.js Application. This is the place to add Vue plugins and to inject functions or constants. Every time you need to use `Vue.use()`, you should create a file in `plugins/` and add its path to plugins in `nuxt.config.js`.

More information about the usage of this directory in [the documentation](https://nuxtjs.org/docs/2.x/directory-structure/plugins).

### `static`

This directory contains your static files. Each file inside this directory is mapped to `/`.

Example: `/static/robots.txt` is mapped as `/robots.txt`.

More information about the usage of this directory in [the documentation](https://nuxtjs.org/docs/2.x/directory-structure/static).

### `store`

This directory contains your Vuex store files. Creating a file in this directory automatically activates Vuex.

More information about the usage of this directory in [the documentation](https://nuxtjs.org/docs/2.x/directory-structure/store).

## Contributing

If you'd like to contribute to this project, please follow the [Contribution Guidelines](CONTRIBUTING.md).

## License

This project is licensed under the [MIT License](LICENSE).
