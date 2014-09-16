# Git WebUI

This git extension offers a web-based user interface for a repository.
It provides history and tree browsing. You may also use this interface to commit
as it comes with a diff review UI and the ability to stage / unstage code.

Moreover as git-webui is also a web server, your repository is accessible to
other people on the same network. They can clone or pull your code using the
same URL.

## Installation

The following command will install git-webui in `$HOME/.git-webui` and add a
`webui` alias to your global `.gitconfig` file

Using curl (Mac OS X):
```
curl https://raw.github.com/alberthier/git-webui/install/installer.sh | bash
```

Using wget (Linux):
```
wget -O - https://raw.github.com/alberthier/git-webui/install/installer.sh | bash
```

Upon installation git-webui will update itself automatically every couple of weeks

## Usage

### Starting

First cd to any of your project versionned with git
```
cd <my-local-git-clone>
git webui
```

This will start an http server and open your default browser with the GUI

### History Viewing

The toolbar on the left shows your branches and tags. The log of the currently selected one is displayed.

When selecting a revision the diff of this specific commit is displayed in the right panel.

On top of the right panel, you can choose 'Tree' to display the versionned content at the specific
revision selected in the left panel. You can browse through directories and display file contents.

### Remote access

Other people on your network have read-only access to your repository: they may clone or pull
from your repository through the same url:

Clone:
```
$ git clone http://<ip_of_the_computer_running_webui>:8000/ repo_name
```

Pull:
```
$ git pull http://<ip_of_the_computer_running_webui>:8000/
```

### Commit

Commits can only be made from localhost.

'Working copy' lists the files modified (compared to the staging area) in your working directory

'Staging area' lists the files modified (compared to HEAD) in your staging area. This is the differencies that will be committed

'Message' lets you enter a commit message

The diff view lets you review the differences of the selected file. In this view:
- Ctrl+Click on an added or removed line stages/unstages the line
- Ctrl+Click on an hunk header (purple lines) stages/unstages the complete hunk

## Dependencies

### Runtime
- git (of course :) )
- python 2.7+ or python 3.0+ (Generally already installed on your Mac / Linux)
- An up-to-date modern browser

### Development
- Runtime dependencies and ...
- node.js
- grunt-cli

## Uninstallation

Using curl (Mac OS X):
```
curl https://raw.github.com/alberthier/git-webui/install/uninstaller.sh | bash
```

Using wget (Linux):
```
wget -O - https://raw.github.com/alberthier/git-webui/install/uninstaller.sh | bash
```

## Author

[Éric ALBER](mailto:eric.alber@gmail.com) ([@eric_alber](https://twitter.com/eric_alber))

## License

This software is licensed under the [Apache 2.0](http://www.apache.org/licenses/LICENSE-2.0.html) license
