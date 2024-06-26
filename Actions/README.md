GitHub Actions makes automation easy!

Improve the quality of your code and make your life more productive through devops!

# [GitHub Actions](https://docs.github.com/en/actions)

Automate, customize, and execute your software development workflows right in your repository with GitHub Actions. You can discover, create, and share actions to perform any job you'd like, including CI/CD, and combine actions in a completely customized workflow.

## [Actions Workflows](https://docs.github.com/en/actions/using-workflows)

A workflow is a configurable automated process that will run one or more jobs. Each job is it's ow

<p align="center">
  <img src="https://user-images.githubusercontent.com/22425467/186950578-0d7c547f-14ad-4d0e-b18d-10edccc92454.svg">
</p>

### [Events that trigger workflows](https://docs.github.com/en/actions/using-workflows/events-that-trigger-workflows)

You can configure your workflows to run when specific activity on GitHub happens, at a scheduled time, or when an event outside of GitHub occurs.

# [Actions](https://docs.github.com/en/actions/learn-github-actions/finding-and-customizing-actions)

Actions are the building blocks that power your workflow. A workflow can contain actions created by the community, or you can create your own actions directly within your application's repository. This guide will show you how to discover, use, and customize actions.

### [Actions Marketplace](https://github.com/marketplace?type=actions)
<img align="right" width="300" src="https://user-images.githubusercontent.com/22425467/186952618-122c9d1c-3db8-4257-9d3d-0027d69d9403.png">

The GitHub Marketplace is a place where you can share your apps and actions publicly with all GitHub users.

Anyone can publish an action in GitHub Marketplace. GitHub verifies some partner organizations and these are shown as verified creators.

## [Status Checks](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/collaborating-on-repositories-with-code-quality-features/about-status-checks)

Status checks let you know if your commits meet the conditions set for the repository you're contributing to.

If status checks are required for a repository, the required status checks must pass before you can merge your branch into the protected branch. For more information, see "[About protected branches](https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/defining-the-mergeability-of-pull-requests/about-protected-branches#require-status-checks-before-merging)."

![image](https://user-images.githubusercontent.com/22425467/186950765-13694463-d883-4661-a9ae-87098009e302.png)

## [Environments](https://docs.github.com/en/actions/deployment/targeting-different-environments/using-environments-for-deployment)
Environments are used to describe a general deployment target like `production`, `staging`, or `development`.

You can configure environments with protection rules and secrets. A workflow job that references an environment must follow any protection rules for the environment before running or accessing the environment's secrets.

# GitHub Actions Best Practices
Best practices to follow when using GitHub Actions.

# Resources

- [Security hardening for GitHub Actions](https://docs.github.com/en/actions/security-guides/security-hardening-for-github-actions)
- [Actions Documentation](https://docs.github.com/en/actions)
- [Community Discussions](https://github.com/orgs/community/discussions/)

# Billing

## Minute Rounding
GitHub [rounds](https://docs.github.com/en/billing/managing-billing-for-github-actions/about-billing-for-github-actions#:~:text=GitHub%20rounds%20the%20minutes%20and%20partial%20minutes%20each%20job%20uses%20up%20to%20the%20nearest%20whole%20minute.) the minutes and partial minutes each job uses up to the nearest whole minute. This means reducing the number of jobs in your workflow will minimize rounding of minute usage and you should take into consideration how long a job will run.

## [Spending limit](https://docs.github.com/en/billing/managing-billing-for-github-actions/managing-your-spending-limit-for-github-actions)
If you care about money, you should definitely set up a budget.

# Development

## [VSCode](https://code.visualstudio.com/)
Your local IDE where you develop.

<!-- ### [YAML](https://marketplace.visualstudio.com/items?itemName=redhat.vscode-yaml)
Get Language/Syntax support using Read Hat's [YAML](https://marketplace.visualstudio.com/items?itemName=redhat.vscode-yaml) extension which utilizes [schemastore.org](https://www.schemastore.org/json/). This will provide tons of features such as syntax highlighting and formatting. -->

### [GitHub Actions VS Code Extension](https://github.com/github/engineering/discussions/2864)
> **Note**
> GitHub Actions VS Code Extension coming soon. For now use the [Old Extension](https://github.com/cschleiden/vscode-github-actions).

### [Copilot](https://github.com/features/copilot/)
Use Copilot for advanced autocompletion. See [How Do I Get Copilot?](https://github.com/austenstone/copilot-demo#how-do-i-get-copilot).

## Debugging
### [Self-hosted](https://docs.github.com/en/actions/hosting-your-own-runners/managing-self-hosted-runners/adding-self-hosted-runners)
GitHub self-hosted runners allow you to make your local development environment the runner of jobs on GitHub. Simply add your machine as a self-hosted runner and use the [label](https://docs.github.com/en/actions/hosting-your-own-runners/managing-self-hosted-runners/using-labels-with-self-hosted-runners) assigned as your runner in the workflow file using [`runs-on`](https://docs.github.com/en/actions/using-workflows/workflow-syntax-for-github-actions#jobsjob_idruns-on).

### [nektos/act](https://github.com/nektos/act)
> **Warning**
> [Self-hosted](#self-hosted) is a much better option for many reasons including the event's context.

`act` allows you to run your workflows/jobs locally using Docker.

### [Codespaces](https://github.com/features/codespaces)
Use the integrated debugger to click the “start debugging” button to begin executing the workflow on a GitHub-hosted runner. You can pause execution manually, or you can set breakpoints in the Codespaces editor, indicating a step in a job where you want to pause execution of the workflow. See [documentation](https://docs.github.com/en/codespaces).

### [Debugging with tmate](https://github.com/marketplace/actions/debugging-with-tmate)
This GitHub Action offers you a direct way to interact with the host system on which the actual scripts (Actions) will run.

## Tools

### [CLI](https://cli.github.com/)
The GitHub CLI provides a terminal interface for all of github including actions. See [run](https://cli.github.com/manual/gh_run) and [workflow](https://cli.github.com/manual/gh_workflow).

# Workflow Usage
When writing workflows there are some things to keep in mind.

## Enforcing workflow with [Branch Protection Rules](https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/managing-protected-branches)
Branch protection rules allow you to enforce workflow for developers by ensuring they meet requirments before merging their code to a specific branch (typically the default branch).

### [Status Checks](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/collaborating-on-repositories-with-code-quality-features/about-status-checks)
You can ensure that certain checks happen in Actions before newly introuced code is merged to a branch. All actions report a status as the name of the workflow file.

#### Some checks Actions is commonly used to perform
- Build
- Test
- Lint
- Static application security testing (SAST)
- Software composition analysis (SCA)

## Reuse Workflows
You should call workflows from other workflows to avoid duplication. Practice innersourcing to promote best practices and reuse welldesigned/tested workflows.

### Why?
- Easier to maintain
- Create workflows more quickly
- Avoid duplication. DRY(don't repeat yourself).
- Build consistently across multiple, dozens, or even hundreds of repositories
- Require specific workflows for specific deployments
- Promotes best practices
- Abstract away complexity

### Example
#### Caller (reusable-caller.yml)
```yml
jobs:
  build:
    uses: ./.github/workflows/reusable-called.yml
    with:
      username: ${{ github.actor }}
```

#### Called (reusable-called.yml)
```yml
on:
  workflow_call:
    inputs:
      username:
        default: ${{ github.actor }}
        required: false
        type: string

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - name: Run a one-line script
        run: echo Hello, ${{ inputs.username }}!
```

## [Composite Actions](https://docs.github.com/en/actions/creating-actions/creating-a-composite-action)
Use a composite action to combine(re-use) multiple steps.

### Why?
For the same reasons mentioned in [Reuse Workflows](#Reuse%20Workflows) but on a step level.

### Example
```yml
runs:
  using: "composite"
```

## Set timeouts
By default a job will be cancelled after 360 minutes or 6 hours. Consider setting a timeout to avoid running jobs for too long.

### Why?
Prevent jobs from hogging the GitHub Actions queue. There are usage limits that can cause other jobs to wait or perform poorly. See [Usage limits](https://docs.github.com/en/actions/learn-github-actions/usage-limits-billing-and-administration#usage-limits).

A timeout can also help catch issues early.

### Example
[`jobs.<job_id>.timeout-minutes`](https://docs.github.com/en/enterprise-cloud@latest/actions/using-workflows/workflow-syntax-for-github-actions#jobsjob_idtimeout-minutes)

```yml
jobs:
  build:
    timeout-minutes: 30
    runs-on: ubuntu-latest
    steps:
      ...
```

## Limit Permissions
The default [`${{ GITHUB_TOKEN }}`](https://docs.github.com/en/actions/security-guides/automatic-token-authentication) has access to most things. Consider limiting permissions.

### Why?
- Prevent accidental access to sensitive information
- Avoid accidental use of destructive actions

### Example
[`permissions`](https://docs.github.com/en/enterprise-cloud@latest/actions/using-workflows/workflow-syntax-for-github-actions#permissions)
#### Permission types
```yml
permissions:
  actions: read|write|none
  checks: read|write|none
  contents: read|write|none
  deployments: read|write|none
  id-token: read|write|none
  issues: read|write|none
  discussions: read|write|none
  packages: read|write|none
  pages: read|write|none
  pull-requests: read|write|none
  repository-projects: read|write|none
  security-events: read|write|none
  statuses: read|write|none
```

#### Permission all
```yml
permissions: read-all|write-all
```

#### No permissions
```yml
permissions: {}
```

## Consider if (third-party) actions are really needed
Actions on the marketplace are written by third-party developers. You should careful consider if you need to use an action. GitHub grants the [verified creator badge](https://docs.github.com/en/developers/github-marketplace/github-marketplace-overview/about-marketplace-badges#for-github-actions) to creators who are [partner organizations](https://partner.github.com/).

### Why?

Third-party actions could break your devops pipeline or even perform malicious actions if precausion is not taken.

### Example
#### Bad
```yml
jobs:
  print:
    runs-on: ubuntu-latest
    steps:
      - uses: phwes/simple_hello_world@v1
```
#### Good
```yml
jobs:
  print:
    runs-on: ubuntu-latest
    steps:
      - run: echo "Hello World"
```

### References
- [Actions Verified ✅](https://github.com/marketplace?type=actions&verification=verified_creator)
- [Actions Published by GitHub 😸](https://github.com/marketplace?type=actions&query=publisher%3Agithub+publisher%3Aactions)
- [Keeping your GitHub Actions and workflows secure Part 1: Preventing pwn requests](https://securitylab.github.com/research/github-actions-preventing-pwn-requests/)
- [Keeping your GitHub Actions and workflows secure Part 2: Untrusted input](https://securitylab.github.com/research/github-actions-untrusted-input/)
- [Keeping your GitHub Actions and workflows secure Part 3: How to trust your building blocks](https://securitylab.github.com/research/github-actions-building-blocks/)

## Pin actions to SHAs
Pin actions to SHAs to ensure that the action is always the same. Consider pinning to the SHA of a tested release.

### Why?
Authors can overwrite branches and tags to point at malicious or breaking code. A SHA is entirely unique and can be used to pin an action to a specific version.

### Example
#### Bad
```yml
      - uses: phwes/simple_hello_world@main
```
#### Good
```yml
      - uses: phwes/simple_hello_world@12d9258754d937b3d2500da69bf531924eaa567a
```

## Consider using concurrency
You can use `jobs.<job_id>.concurrency` to ensure that only one job is running at a time. The parameter `cancel-in-progress` will also cancel any other jobs in the same concurrency group.

### Why?
You only want one deployment to run at a time and you always want to deploy the latest code. Also you sometimes don't need to run CI on intermediate commits when newer code has been pushed. Any use case that requires a mutex is a good candidate for concurrency.

### Example
```yml
concurrency: 
  group: ${{ github.workflow }}-${{ github.ref }}
  cancel-in-progress: true
```

### Refernces
- [Using concurrency](https://docs.github.com/en/actions/using-jobs/using-concurrency)

## Keep Secrets as Environment Variables
To help protect secrets, consider using environment variables, STDIN, or other mechanisms supported by the target process.

### Why?
Command-line processes may be visible to other users (using the ps command) or captured by security audit events.

### Example
#### Bad
```yml
steps:
  - name: Run a one-line script
    run: echo Hello, ${{ secret.name }}!
```

#### Good
```yml
steps:
  - name: Run a one-line script
    env:
      NAME: ${{ secret.name }}
    run: echo Hello, $NAME!
```
### References
[Using encrypted secrets in a workflow](https://docs.github.com/en/actions/security-guides/encrypted-secrets#using-encrypted-secrets-in-a-workflow)

## Prefer using OIDC Connect
Consider using OIDC Connect to interact with the cloud.

### Why?
Long-lived credentials are insecure and OIDC Connect allows the use of short-lived access tokens.

### Notes
The OIDC subject contains metadata such as org/repo/environment that you can use to [Configuring the role and trust policy](https://docs.github.com/en/enterprise-cloud@latest/actions/deployment/security-hardening-your-deployments/configuring-openid-connect-in-amazon-web-services#configuring-the-role-and-trust-policy). This can be used to control which branches get access.

### References
- [Security hardening your deployments](https://docs.github.com/en/actions/deployment/security-hardening-your-deployments)
- [Configuring OpenID Connect in cloud providers](https://docs.github.com/en/actions/deployment/security-hardening-your-deployments/configuring-openid-connect-in-cloud-providers)
- [Using OpenID Connect with reusable workflows](https://docs.github.com/en/actions/deployment/security-hardening-your-deployments/using-openid-connect-with-reusable-workflows)

## Careful with `pull_request_target` event trigger
You can check out external PRs when using the [`pull_request_target`](https://docs.github.com/en/actions/using-workflows/events-that-trigger-workflows#pull_request_target) event trigger. This means you are giving write access and secret access to untrusted code. This could compromise your entire repository and any resources connected to Actions.

### Example
#### Bad
> **Warning**
> We are checking out code on the target repo and executing code from the pull request.
```yml
name: my action
on: pull_request_target

jobs:
  pr-check: 
    name: Check PR
    runs-on: ubuntu-latest
    steps:
      - name: Setup Action
        uses: actions/checkout@v3
        with:
          ref: ${{github.event.pull_request.head.ref}}
          repository: ${{github.event.pull_request.head.repo.full_name}}
      ... execute code from the pull request ...
```
