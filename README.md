## Create Release Pull Request
This action helps to create the release candidate branch and the pull request.

To implement this action the following input values needs to be passed

* GITHUB_TOKEN: Github Token
* VERSION_NAME: New Release Version Name
* IS_CIVICRM_EXTENSION: If it is a CiviCRM extension. It updates the info.xml if its true.
* FILE_UPDATE_COMMIT_DESC: Commit name to update the file mentioned in Replace command
* RELEASE_PR_TITLE: Title for the Release Pull Requests to be created
* RELEASE_PR_IDENTIFIER_LABEL: Label to Identify Release Pull Request


```yml
name: Create Release Pull Request

on:
  workflow_dispatch:

jobs:
  Test:
    runs-on: ubuntu-latest
    steps:
      - uses: compucorp/release-pr-action@<version>
        with:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
          VERSION_NAME: 2.10.0
          IS_CIVICRM_EXTENSION: true
          FILE_UPDATE_COMMIT_DESC: "Update info.xml"
          RELEASE_PR_TITLE: "Release v2.10.0"
          RELEASE_PR_IDENTIFIER_LABEL: release
```

