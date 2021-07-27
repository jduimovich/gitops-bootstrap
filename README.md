# gitops-bootstrap
Empty Starter Repo for Bootstrapping a gitops repoistory using the Github Actions bootstrapper

To use this template, you can use the Github Web UI or the following CLI commands with the gh cli.

```

gh repo create demo -p https://github.com/jduimovich/gitops-bootstrap-template

(reply yes to a local copy, otherwise clone it first)

cd demo

set-secret.cmd (or sh on linux)

kick off the workflow with this cli (or use the GH UI to run workflow)

gh workflow run export-submit-pr.yml 

Watch the workflow run 
gh run list --workflow=export-submit-pr.yml

```

A successful run will issue a pull request for the exported files.

If you merge the pull request, it will be deployed back to the cluster.

A CI integration workflow is also included to automatically deploy all changes pushed to the repo.

