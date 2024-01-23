# Community Bulma Styles

Customized Bulma styling for DigitalOcean Community tools.

---

## Development/Building

To setup the build/develop environment, you will need to having Node.js installed (matching the version specified in
 `.nvmrc`), and then run `npm ci` to install dependencies (this will respect the lockfile).

We make use of `sass-lint` to maintain code quality in the SCSS files.
To run this you can use `npm test`.

A demo project is included in the `demo` directory, which helps ensure the styles are working as expected.
This can be run with `demo:dev` to start a server with hot reloading, or `demo:build` to build the demo project.

## Usage Example

This styling package is being used in the [DigitalOcean Community DNS tools](https://github.com/do-community/dns-tool),
 which act as a great example of what customisations this package provide on top of Bulma, and how it integrates
 seamlessly into the DigitalOcean Community website.

## Source Structure

### [`src/components`](./src/components)

This directory contains all the styling components that are available within `.do-bulma`.

### [`src/globals`](./src/globals)

This directory contains all the styling that is applied to the whole page.

## Contributing

If you are contributing, please read the [contributing file](CONTRIBUTING.md) before submitting your pull requests.
