<div style="display: inline-block;">
<a class="link" href="http://oclipa.github.io/">&lt; home</a>
<a class="link" href="http://oclipa.github.io/toolbox.html">&lt; toolbox</a>
</div> 

## Python

<button type="button" id="toggle-all" value="none">Expand All Sections</button>

-------------------------------------------------------------------------------------------------------

<div id="install">
<button type="button" class="collapsible">+ Installation</button>
<div class="content" style="display: none;" markdown="1">
1. Run the following: `echo -e 'if command -v pyenv 1>/dev/null 2>&1; then\n  eval "$(pyenv init -)"\nfi' >> ~/.zshrc` (or `~/.bashrc`)

**MacOS**

1. Install [Homebrew](https://brew.sh/): `/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"` 
1. If necessary, remove previous installs of python:
   * **Do not uninstall the system version of python, found in /usr/bin**
   * Check for installed versions: `where python python2 python3`
1. Install pyenv: `brew install pyenv`
   * You may also need to run: `brew install openssl readline sqlite3 xz zlib`
1. Verify the installation by running: 
   * `pyenv update`
1. Run the following to ensure pyenv gets initialized: 
   * `echo -e 'if command -v pyenv 1>/dev/null 2>&1; then\n  eval "$(pyenv init -)"\nfi' >> ~/.zshrc` (or `~/.bashrc`)
</div>
</div>

**Ubuntu**

1. Install pre-requisites:
   * `sudo apt-get install -y build-essential libssl-dev zlib1g-dev libbz2-dev libreadline-dev libsqlite3-dev wget curl llvm libncurses5-dev libncursesw5-dev xz-utils tk-dev libffi-dev liblzma-dev python-openssl git`
1. Install pyenv:
   * `curl https://pyenv.run | bash`
1. Reopen the prompt (or run `exec $SHELL`)
   * If there are errors related to config files, check their permissions (they should be 644).
1. Verify the installation by running: 
   * `pyenv update`
1. Run the following to ensure pyenv gets initialized: 
   * `echo -e 'if command -v pyenv 1>/dev/null 2>&1; then\n  eval "$(pyenv init -)"\nfi' >> ~/.zshrc` (or `~/.bashrc`)

**Setting a Global Python Version**

*It is usually cleaner to create a virtual environment (see below), rather than using a base installation*

1. Install your chosen version of python:
   * List available versions (in this case, list all from 3.6-3.8): `pyenv install --list | grep " 3\.[678]"`
   * Install the chosen version: `pyenv install 3.8.2` (latest at time of writing)
1. Set this version of python as the global default: `pyenv global 3.8.2`
1. Verify active version: `pyenv version`

**Creating a Python Virtual Environment**

*A virtual environment allows an app to be configured without affecting the base installation*

1. Create the virtual environment for your chosen (installed) version:
   * `pyenv virtualenv 3.8.3 [identifier-for-venv]`
1. To set the venv as the global default:
   * `pyenv global [identifier-for-venv]`
1. To set the venv as the local default (which overrides the global default):
   * `pyenv local [identifier-for-venv]`
1. To unset the venv and revert to the gloabl default:
   * `pyenv local --unset`
1. It is also possible to chain versions, so that if venv1 is missing, venv2 will be used:
   * `pyenv [global|local] [identifier-for-venv1] [identifier-for-venv2]`

</div>
</div>

<div id="uninstall">
<button type="button" class="collapsible">+ Uninstallation</button>
<div class="content" style="display: none;" markdown="1">

**Do not uninstall the system version of python, found in /usr/bin/ or /System/**
1. Add the following to .bashrc or .zshrc:

```
export PATH="/home/dev/.pyenv/bin:$PATH"
if command -v pyenv 1>/dev/null 2>&1; then
  eval "$(pyenv init -)"
  eval "$(pyenv virtualenv-init -)"
fi
```

**Using pyenv**

If python has been installed using pyenv:

* pyenv uninstall [version]
* or, more manually, 
   * Identify the location of the version to be deleted: `pyenv prefix 3.8.2`
      * This should be a location in `~/.pyenv`.
   * Delete the directory: `rm -rf [directory path]`

**Using Homebrew**

If python was install using Homebrew:
   * Check if a version is installed: `brew list | grep python`
   * Check the install location using: `brew info python`
   * Uninstall using: `brew uninstall --ignore-dependencies python``

If you have problems, run `brew doctor` and see if any of the suggestions help.
   * If you have permissions issues, try running the following command: `sudo chown -R $(whoami):wheel /usr/local`
   * If you have problems with an pre-existing installation of `node`, delete the following files and directories and then re-install using `brew install node` (see [here](https://stackabuse.com/how-to-uninstall-node-js-from-mac-osx/))
      * ~/.npmrc
      * ~/.npm
      * ~/.node-gyp
      * ~/.node_repl_history
      * /usr/local/bin/node 
      * /usr/local/bin/node-debug
      * /usr/local/bin/node-gyp
      * /usr/local/include/node 
      * /usr/local/include/node_modules 
      * /usr/local/lib/dtrace/node.d
      * /usr/local/lib/node 
      * /usr/local/lib/node_modules 
      * /usr/local/share/doc/node
      * /usr/local/share/man/man1/node*
      * /usr/local/share/man/man1/npm*
      * /usr/local/share/systemtap/tapset/node.stp
      * /opt/local/include/node 
      * /opt/local/lib/node_modules
      * /opt/local/node 
      * /opt/local/share/doc/node 

**Manually**

If an independently installed version of python is present, delete the following files and directories (see [here](https://apple.stackexchange.com/questions/284824/remove-and-reinstall-python-on-mac-can-i-trust-these-old-references)):

* /usr/local/bin/python*
* /usr/local/bin/pip*
* /Library/Frameworks/Python.framework
  * NOTE: do not delete **/System**/Library/Frameworks/Python.framework!

</div>
</div>

<div id="furtherinfo">
<button type="button" class="collapsible">+ Further Information</button>
<div class="content" style="display: none;" markdown="1">

* [https://github.com/pyenv/pyenv-installer/blob/master/README.rst](https://github.com/pyenv/pyenv-installer/blob/master/README.rst)
* [https://github.com/pyenv/pyenv/blob/master/COMMANDS.md](https://github.com/pyenv/pyenv/blob/master/COMMANDS.md)
* https://github.com/pyenv/pyenv-virtualenv/blob/master/README.md](https://github.com/pyenv/pyenv-virtualenv/blob/master/README.md)

</div>
</div>

&nbsp;

&nbsp;

&nbsp;

-------------------------------------------------------------------------------------------------------

**Move along; nothing to see here...**

<script type="text/javascript">

    const loadCSS = (filename) => { 

       const file = document.createElement("link");
       file.setAttribute("rel", "stylesheet");
       file.setAttribute("type", "text/css");
       file.setAttribute("href", filename);
       document.head.appendChild(file);
    };

    const loadJS = (filename) => { 

       const file = document.createElement("script");
       file.setAttribute("type", "text/javascript");
       file.setAttribute("src", filename);
       document.head.appendChild(file);
    };
   
    //just call a function to load your CSS
    //this path should be relative your HTML location
    loadCSS("../collapse.css");
    loadJS("../collapse.js");

</script>
