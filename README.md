# library-builder

This action is used to clone multiple private repositories into a runner for use in a Job.

## How to use this Action

```
      - name: Build Library
        uses: GannettDigital/actions-library-builder@main
        with: 
          repo_owner: GannettDigital
          repo_list: "cloud-engineering-actions,appops-actions"
          repo_version: main
          private_action_token: ${{ secrets.PRIVATE_ACTION_TOKEN }}
```


## Inputs
- **repo_owner**
  - The name of the Organization to pull these repos from.
  - #### **NOTE: You can only use this Action once per Github Org as each one requires its own PAT `.`
- **repo_list**
  - The CSV list of the repositories you'd like to clone.  Composite actions do not accept Arrays so it must be a String.
  - Example: my-repoA,my-repoB. 
- **repo_version**
  - The version of the repo to clone for each repository.
- **private_action_token**
  - Your Access Token for the organization/repo(s).  This value is obfuscated.

## Outputs
None.

## ToDo
* Add `repo_version` for each repository, IE my-repoA@main,myrepoB@1.0.0
