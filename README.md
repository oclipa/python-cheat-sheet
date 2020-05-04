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

**MacOS**

1. Install [Homebrew](https://brew.sh/): `/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"` 
1. If necessary, remove previous installs of python:
   * **Do not uninstall the system version of python: /usr/bin/python\* **
   * Check for installed versions: `where python python2 python3`
1. Install pyenv: `brew install pyenv`
   * You may also need to run: `brew install openssl readline sqlite3 xz zlib`
1. Install your chosen version of python:
   * List available versions (in this case, list all from 3.6-3.8): `pyenv install --list | grep " 3\.[678]"`
   * Install the chosen version: `pyenv install 3.8.2` (latest at time of writing)
1. Set this version of python as the global default: `pyenv global 3.8.2`
1. Verify: `pyenv version`
1. Give pyenv power over your shell's PATH: `echo -e 'if command -v pyenv 1>/dev/null 2>&1; then\n  eval "$(pyenv init -)"\nfi' >> ~/.zshrc`
</div>
</div>

<div id="uninstall">
<button type="button" class="collapsible">+ Uninstallation</button>
<div class="content" style="display: none;" markdown="1">

**Do not uninstall the system version of python, found in /usr/bin/ or /System/**

**Using pyenv**

If python has been installed using pyenv:

* pyenv uninstall <version>
* or, more manually, 
   * Identify the location of the version to be deleted: `pyenv prefix 3.8.2`
      * This should be a location in `~/.pyenv`.
   * Delete the directory: `rm -rf <directory path>`

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
