A demo repository with a book store API example.

## Local usage
- Run `optic run` on the main branch
- make some changes to `openapi.yml`
- run `optic run` again.

## CI setup
The repo is setup with Gitlab CI and Github Action configuration files:
- fork the repository
- grab an Optic organization token from the `tokens` tab in the [Optic webapp](https://app.useoptic.com/) and set it as `OPTIC_TOKEN` in your CI env
- add a `GITHUB_TOKEN` or `OPTIC_GITLAB_TOKEN` with comment permission to your CI env (more about this [in the docs](https://useoptic.com/docs/setup-ci#configure-commenting-on-pull-requests-optional))
- create a pull request containing breaking changes in `openapi.yml` to see Optic in action.

## Advanced
- Configure custom governance rules in `optic.yml`: read [the docs](https://useoptic.com/docs/lint-openapi)
