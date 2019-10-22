# Contributing

## Pull Requests

### Creating a Pull Request

This application has been designed so that people can easily expand it.
To request us to review code that you create, you will need to create a pull request.
Creating a pull request is described in
 [this tutorial](https://www.digitalocean.com/community/tutorials/how-to-create-a-pull-request-on-github).

### Linting

Before creating a pull request to this application, you will want to lint it first.
This is because linting is a check that is ran when a pull request is made and cannot be merged in if it fails.

To lint, simply run `npm run lint`.

This project enforces LF line styles, 4 spaces and no semi-colons.
The linting will fail if this is not followed.

### File Location/Types

Anything that is meant to be used as a styling component and only be available within `.do-bulma` should be located
 within [`src/components`](./src/components) with a file name that indicates sensibly what is contained.
Any styling that should affect the page as whole should live within [`src/globals`](./src/globals).
Global variables and mixins etc. should also live within the `globals` directory. 

## Issue Creation

In the event that you have a issue using the styling or have a suggest for a change but don't want to contribute code,
 we are more than happy to help. Make sure that when you create your issue, you include as much information as possible
 so that we can get to work on resolving it immediately.
