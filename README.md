# gitops-bootstrap
Empty Starter Repo for Bootstrapping a gitops repoistory using the Github Actions bootstrapper

To use this bootstrap workflow you need to be logged into a OpenShift Cluster and select the project you want to export.

To use this example, you can use the Github Web UI or the following CLI commands to create your own empty gitops repository.

Create the repository from the template, this will pre-populate the workflows for Gitops. If you want to use ArgoCD to "pull" changes, you can disable the CI Deploy in Github, and configure argocd to recursively deploy the `export` directory. 
``` 
gh repo create demo -p https://github.com/jduimovich/gitops-bootstrap-template
```
Note, reply yes to a local copy or to use the following steps, manually clone the repo you just created.


Kick off the workflow with the  cli (or use the GH UI to manually run an export)
```
cd demo 
set-secret.cmd 
gh workflow run export-submit-pr.yml 
```

Watch the workflow run  

```  
gh run list --workflow=export-submit-pr.yml 
```

A successful run will issue a pull request for the exported files. If you merge the pull request, it will be deployed back to the cluster.

A CI integration workflow is also included to automatically deploy all changes pushed to the repo.

