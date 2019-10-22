# Community Bulma Styles

Customized Bulma styling for DigitalOcean Community tools.

---

## Development/Building

To setup the build/develop environment, you will need to run `npm i` with Node 12+ installed.
This will install the dependencies to allow you to build the project.

If you wish to build the styles to CSS, simply run `npm run build`.
This will output `style.css` into `build`.

We make use of `sass-lint` to maintain code quality in the SCSS files.
To run this you can use `npm run lint`.

To test the project fully, we first run the linter and then build the SCSS to ensure it is valid.
This is achieved with `npm test`.

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
