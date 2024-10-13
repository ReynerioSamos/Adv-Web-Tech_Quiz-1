# Quiz 1 Group Members:
Reynerio Samos (2018119235),
Duane Arzu (2020152202)

Sources:
- [About pull requests - GitHub Docs](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-pull-requests)
- [git-request-pull - git docs](https://git-scm.com/docs/git-request-pull)
---
## Syntax and Example
Syntax:
```bash
git request-pull [-p] <start> <URL> [<end>]
```
Example:
```bash
git request-pull v1.0 https://github.com/<USERNAME>/<REPO> main
```
## Definition:
A pull request is a proposal to merge a set of changes from one branch into another. In a pull request, collaborators can review and discuss the proposed set of changes before they integrate the changes into the main codebase. Pull requests display the differences, or diffs, between the content in the source branch and the content in the target branch. 

`git request-pull` Generate a request asking your upstream project to pull changes into their tree. The request, printed to the standard output, begin with the branch description, summarizes the changes, and indicates from where they can be pulled.

The upstream project is expected to have the commit named by `<start>` and the output asks it to integrate the changes you made since that commit, up to the commit named by `<end>`, by visiting the repository named by `<URL>`.
## Options:
- `p` : Include patch text in the output
- `<start>` : Commit to start at. This names a commit that is already in the upstream history.
- `<URL>` : The repository URL to be pulled from.
- `<end>` : Commit to end at (defaults to HEAD). This names the commit at the tip of the history you are asking to be pulled.

## Typical git request-pull use case
Integrate your current working branch into a remote project's branch (in this case `main`) and then run a git request-pull 
```bash
git push https://github.com/<USERNAME>/<REPO> main
git request-pull v1.0 https://github.com/<USERNAME>/<REPO> main
```
this will produce a request to the upstream, summarizing changes from remote's `v1.0` release and local's `main` to pull it from remote's repository
