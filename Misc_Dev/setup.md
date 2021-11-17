# Computer Setup

### Mac
New to programming on mac, don't worry we got you covered 🥳

- Install xcode-select  

  To install `xcode-select` follow the following steps :-  

  1. Open the terminal, use shortcut `command + space` and type terminal in the search 

  2. Run the Command

      ```bash
      $ xcode-select --install
      ```

  3. When prompted, enter the login password

  4. To check for successful, type  `xcode-select`. You should see something like:-

      ```bash
      $ xcode-select
      
      xcode-select: error: no command option given
      Usage: xcode-select [options]
      
      Print or change the path to the active developer directory. This directory
      controls which tools are used for the Xcode command line tools (for example, 
      xcodebuild) as well as the BSD development commands (such as cc and make).
      
      Options:
        -h, --help                  print this help message and exit
      .
      .
      ```

- Install Homebrew

  1. Open `Terminal` 

  2. Paste this line and hit enter

     ```bash
     $ /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
     ```

  3. Type `brew doctor` to confirm successful install type:-

     ```bash
     $ brew doctor
     Your system is ready to brew
     ```

- Install Git

  1. Open `Terminal` and type :-

     ```bash
     $ brew install git
     ```

  2. Type `git` to confirm success, you see this on output :-

     ```bash
     $ git
     
     usage: git [--version] [--help] [-C <path>] [-c <name>=<value>]
                [--exec-path[=<path>]] [--html-path] [--man-path] [--info-path]
                [-p | --paginate | -P | --no-pager] [--no-replace-objects] [--bare]
                [--git-dir=<path>] [--work-tree=<path>] [--namespace=<name>]
                [--super-prefix=<path>] [--config-env=<name>=<envvar>]
                <command> [<args>]
     
     These are common Git commands used in various situations:
     
     start a working area (see also: git help tutorial)
        clone             Clone a repository into a new directory
        init              Create an empty Git repository or reinitialize an existing one
        .
        .
     
     ```

- Configure Git

  1. Open `Terminal` 

  2. Type the following to set up your git configuration: - ( Replace with your **name and email** )

     ```bash
     git config --global user.name "<your name>"
     git config --global user.email <your email>
     git config --global init.defaultBranch main
     git config --global pull.rebase false
     ```

  3. Type `git config --list` to verify. Checkout for this output :-

     ```bash
     $ git config --list
     core.repositoryformatversion=0
     core.filemode=true
     core.bare=false
     credential.helper=osxkeychain
     user.name=<your name>
     user.email=<your email>
     init.defaultbranch=main
     pull.rebase=false
     ```

- Add Github SSH 

  We are assuming that you already have a github account.  

  1. Generate a New Key
  2. Add the new key to your system
  3. Copy `public key` 
  4. Add key to Github
  5. Verify if the configuration worked.

- Install rbenv

- Install NVM

- Install PostgresQL

## Installations For Productivity

- [Rectangle](https://rectangleapp.com)
- [Caffeine](https://www.macupdate.com/app/mac/24120/caffeine) (free) can also download Caffeinated on AppStore for a charge.

