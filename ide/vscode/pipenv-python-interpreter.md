### How to configure VSCode's python interpreter to use a virtualenv created by pipenv.

This can be useful for having vscode autoexec things like `black` on save.

1. If the project doesn't already have a Pipfile, create one (and the associated virtualenv) using `pipenv shell`
2.  This creates a unique virtualenv in `~/.virtualenvs/` - it will have your repo's name at the front of it and then some random characters
3.  If creating with pipenv, the success message will have a link to this dir, grab it onto the clipboard. Otherwise, look it up in `~/.virtualenvs`
4.  Cd into your project's new virtualenv folder and copy a link to the python binary (e.g. `/home/jay/.local/share/virtualenvs/florp-bxobuhxj/bin/python`)
5.  Click the Python version at the bottom left corner of VS Code - it will bring up a list of interpreters. If you see your new one, click on it!
6.  If it's not picked up (for instance using bash on windows subsytem), you'll need to tell vscode where to look: open user settings and add this dir to your `venv path`.
7.  Now go pick it from the list
8.  This will set this up as a workspace (project) specific settings file in a `.vscode` dir. VsCode should choose the correct interpeter each time you open the project.

[More info here](https://code.visualstudio.com/docs/python/environments#_where-the-extension-looks-for-environments)
