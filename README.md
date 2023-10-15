Learn the Optic CLI: 

*Install:*
```
npm install @useoptic/optic
```

## Optic documents your API changes 

Optic helps you keep your OpenAPI specification accurate. Your API tests are run through Optic's proxy. When existing endpoints have changed, Optic lets you know and makes it easy to patch the specification. When new endpoints are added, Optic helps you document them. 

Run this command:

```
optic capture openapi.yml
```

This will run some tests and tell you about the API diffs it observed. It will exit 1 (like a snapshot test) because the spec is out of date. 

Now run it again with the `--update` flag. 

```
optic capture openapi.yml --update interactive
``` 

- The CLI will ask you if you want to document and start tracking the behavior of the new `GET /author/{author_id}` in your OpenAPI specification. Say yes. 
- The CLI will patch the schemas to resolve the previous errors. Now your spec is up-to-date!

## Test that API changes follow your style guide

Optic's `diff` command tests that API changes are backwards compatible, and that new and existing API endpoints follow your style guide. The style guide is configured in the `optic.yml` file. 

Run: 

```
optic diff openapi.yml --check --web
```

A visual API Changelog is generated and opened in your browser. It shows you exactly which endpoints were changed, and flags any design or compatibility issues:

![alt](https://www.useoptic.com/changelog2.jpg)

## Other things to try
- Make a breaking change (like adding a required query parameter)
- [Configure an API Style guide](https://useoptic.com/docs/style-guide)
- Try Optic in your own repo
- Check out the example GitHub Actions and GitLab CI workflow files to see how Optic runs in your CI.  

---

## Simulate a CI Run
Optic is designed to run in Pull Requests and give developers actionable feedback on their APIs changes before they merge. You can see what this looks like by running `optic run` locally. It finds all the OpenAPI specifications in your repository, checks that the specs are accurate, and then runs the breaking change + governance checks. 

```bash
optic run
```

You'll see a link to the changelog in the CI output and a link to your API documentation on Optic Cloud: 

![alt](http://localhost:3000/img/bookstore.png)

## Add Optic to your CI setup
The repo is setup with Gitlab CI and Github Action configuration files:
- fork the repository
- grab an Optic organization token from the `tokens` tab in the [webapp](https://app.useoptic.com/) and set it as `OPTIC_TOKEN` in your CI env
- add a `GITHUB_TOKEN` or `OPTIC_GITLAB_TOKEN` with comment permission to your CI env (Optional but recommended. More about this [in the docs](https://useoptic.com/docs/setup-ci#configure-commenting-on-pull-requests-optional))
- create a pull request containing breaking changes in `openapi.yml` to see Optic in action

[Full instructions here](https://useoptic.com/docs/setup-ci)