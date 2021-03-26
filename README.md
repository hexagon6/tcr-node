# TCR with node.js

> based on https://xp123.com/articles/tdd-tcr-commits/ and inspired by https://www.youtube.com/watch?v=IIKndRX5qHw

## requirements
- git
- vscode
- vscode extension: [emeraldwalk.runonsave](https://marketplace.visualstudio.com/items?itemName=emeraldwalk.RunOnSave)

## quickstart
> Launch VS Code Quick Open (Ctrl+P), paste the following command, and press enter.
- `code .`
- copy `ext install emeraldwalk.RunOnSave`
- edit a mjs file and save it, tcr should run
- click on OUTPUT tab on panel, select "Run On Save" in dropdown to see tcr feedback

## start a new project without this git history

1. clone this repo without a git folder
```bash
cd your-project-folder
npx degit https://github.com/hexagon6/tcr-node.git#main .
> cloned hexagon6/tcr-node#main
```

## working with git branches
### initial preparation
0. preparee a new git repo
`git init`

0. b) don't forget to configure your name and email if you haven't done it before or globally
```bash
git config user.email "me@example.com"
git config user.nae "Me Example"
```

0. do your first commit to start the project
`git commit -am "init project"`

### workflow
1. change to your feature-branch
`git checkout -b feature-branch`

2. do your work in TCR fashion:
  - every time you save a file with `.mjs` extension, tests are run
  - A) if no error happened, then all your files are committed with a "working" message
  - B) if an error happened, then all your state is reset to the commit before

3. once your feature is complete you can give it custom git commit messages or squash it if you want a meaningful git history.

4. push to your remote and do a Merge Request (gitlab) or Pull Request (github)

## customization
If you want to run a different command on save, change the match rule (regex) or cmd (string) in `.vscode/settings.json` under key "emeraldwalk.runonsave".
