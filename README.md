# winget-package-submission
This repository contains a workflow to automate the upgrade of a winget package.
You can find more information in this [article](https://www.techwatching.dev/posts/wingetcreate).

## Using this workflow

To use this workflow, you have to:
- copy-paste the `.github/workflows/winget-submission.yml` file in your github repository
- generate a PAT with the scope `public_repo` and add it to the secrets of your project with the name `Project_PAT`
- replace the environment variable value `packageFileName` with the filename of your package in the GitHub releases of your project 
- replace the environment variable value `packageId` with the identifier of your package in Windows Package Manager

## Windows Package Manager Manifest Creator

This workflow uses [Windows Package Manager Manifest Creator](https://github.com/microsoft/winget-create) to update and submit a new version of a package manifest

## Workflow trigger

The workflow is triggered each time a release is published. The idea behind that is to have a new package submitted when a new version of the package has been released.

## GitHub Actions

The only GitHub Action used for this workflow is the shell runner action, which is powershell core here as the workflow runs on windows-latest.
