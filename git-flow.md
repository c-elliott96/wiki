# About: [git flow][git flow]
## Usage: git flow [options] where __options__ are
* init, feature, bugfix, release, hotfix, support, version, config, log

## git flow init
* Before using git flow, we must first init that git repo with `git flow init`
  * This will prompt us for some set up information. The only non-default value will be stating the production branch, which will typically be `master`

    ``` 
      Which branch should be used for bringing forth production releases?
      - develop
      Branch name for production releases: [] master
    ```
  * The rest of the interactive questions can typically be left as default. 

## Creating feature/release/hotfix/support branches
* To list/start/finish feature branches, use: 

  ``` 
  git flow feature
  git flow feature start <name> [<base>]
  git flow feature finish <name>
  ``` 

  For feature branches, the `<base>` arg must be a commit on `develop`.

* To push/pull a feature branch to the remote repository, use:

  ```
  git flow feature publish <name>
    git flow feature pull <remote> <name> 
  ```

* To list/start/finish release branches, use: 

  ```
  git flow release
  git flow release start <release> [<base>]
  git flow release finish <release>
  ```
  For release branches, the `<base>` arg must be a commit on `develop`.

* To list/start/finish hotfix branches, use: 

  ```
  git flow hotfix
  git flow hotfix start <release> [<base>]
  git flow hotfix finish <release>
  ```
  For hotfix branches, the `<base>` arg must be a commit on `master`.

* To list/start support branches, use: 

  ```
  git flow support
  git flow support start <release> <base>
  ```
  For support branches, the `<base>` arg must be a commit on `master`. 

---
#### Supplemental reading: Vincent Driessen's [branching model][bm]. 

[git flow]: https://github.com/nvie/gitflow
[bm]: https://nvie.com/posts/a-successful-git-branching-model/