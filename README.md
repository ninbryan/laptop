setting up preferred workspace environment

## Node.js

There are different installation processes, and the normal way is clicking yes many times and/or click & dragging the icon to the Application folder. There will be times I may forget to setup the `Environment Variables` or the `$PATH`.

### Node.js Setup For Mac

expect to install

- [Homebrew](https://brew.sh/)
- [nvm - Node Version Manager](https://github.com/creationix/nvm)
- [Node.js](https://nodejs.org/)

expect to overwrite `~/.bashrc`

#### The quick bash snippet to install on Mac!

You will need to open the terminal
click `command + space` > type `terminal` > click `enter`

```sh
# install brew
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
brew install nvm
cd ~ # go to HOME directory
echo '# This loads nvm
export NVM_DIR="$HOME/.nvm"
nvm_sh_dir=`brew --prefix nvm`
[ -f "$nvm_sh_dir/nvm.sh" ] && . "$nvm_sh_dir/nvm.sh"
unset nvm_sh_dir
' >> ~/.bashrc
# start using nvm
source ~/.bashrc
nvm install 8.4.0
nvm alias default 8.4.0

```

### Node.js Setup For Windows

expect to install

- [Chocolatey - The package manager for Windows](https://chocolatey.org/)
- [nvm for windows](https://github.com/coreybutler/nvm-windows)
  - [important notes](https://github.com/creationix/nvm#important-notes)
- [Node.js](https://nodejs.org/)

#### The quick batch snippet to install on Windows!

Open `Command Prompt` as Administrator.
Right clicking shows the menu option.

```bat
@"%SystemRoot%\System32\WindowsPowerShell\v1.0\powershell.exe" -NoProfile -InputFormat None -ExecutionPolicy Bypass -Command "iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))" && SET "PATH=%PATH%;%ALLUSERSPROFILE%\chocolatey\bin"
choco install -y nvm
nvm install 8.4.0
nvm alias default 8.4.0

```

After installing `choco`, make life in Windows easier with the 
Running this script will include [Git](https://git-scm.com/) and [Git BASH](https://git-for-windows.github.io/)
```bat
choco install -y git
```
click `start` > type `git bash` > select the software 

### Node.js Confirm Installation

Running these commands should confirm that they are installed and ready to use

```sh
node --version
npm --version

```
