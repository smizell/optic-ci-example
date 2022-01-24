## Optic CI Example

A repository to show how Optic CI works on pull requests. It contains an OpenAPI example (the gist routes for GitHub's API) and a GitHub Action to run the [Optic CI default rules](https://github.com/opticdev/optic-ci-starter/) against them. On every pull request, changes to the OpenAPI file in the pull request branch are compared against the base branch. Optic looks for breaking changes to the API, and reports those in the Pull Request. This status may also be used to fail a merge. Optic also uploads the changelog to the Optic Cloud, where your team can review a semantic diff of the OpenAPI file changes.

For an interactive demo, [sign up](https://www.useoptic.com/) for the Optic Beta on our home page. We'll reach out with more information.

### Try it yourself!

You can see Optic CI in action yourself in just a few steps:

- Open a [pull request](https://github.com/opticdev/optic-ci-example/compare) against the repository.
- In GitHub, edit `api.github.com.gists.yaml`. There's no need to clone the repository - we selected the gist subset of routes so that it's editable right in the browser.
    - When making edits, make sure to make at least one change that would break existing consumers. For example, try making a parameter required.
- Commit your OpenAPI edit. The Optic CI action will run against your pull request, and pass or fail accordingly.
    - Your pull request will get a comment showing what rules passed and failed, and link to the changelog in Optic Cloud.
    - View your code changes - rule failures will be annotated inline, so you know where to go to fix them.
    - Want more detail? Check the action run log!
- Fix your breaking changes in a new edit, and commit that. Watch the status go from red to green.

Congratulations! You caught and fixed a breaking change before it got merged in.