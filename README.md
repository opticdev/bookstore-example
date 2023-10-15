A demo repository with a bookstore API example.

## Local usage
- [install the Optic CLI](https://www.useoptic.com/docs)
- run `optic run`
- make some changes to `openapi.yml`
- run `optic run` again

## CI setup
The repo is setup with Gitlab CI and Github Action configuration files:
- fork the repository
- grab an Optic organization token from the `tokens` tab in the [webapp](https://app.useoptic.com/) and set it as `OPTIC_TOKEN` in your CI env
- add a `GITHUB_TOKEN` or `OPTIC_GITLAB_TOKEN` with comment permission to your CI env (Optional but recommended. More about this [in the docs](https://useoptic.com/docs/setup-ci#configure-commenting-on-pull-requests-optional))
- create a pull request containing breaking changes in `openapi.yml` to see Optic in action

## Advanced `run` configuration
- [API governance](https://useoptic.com/docs/style-guide)
- [API contract testing](https://www.useoptic.com/docs/verify-openapi)
