# Computer Setup

### Mac
New to programming on mac, don't worry we got you covered 🥳

- **Install xcode-select**  

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

- **Install Homebrew**

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

- **Install Git**

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

- **Configure Git**

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

- **Add Github SSH** 

  We are assuming that you already have a github account.  

  1. Generate a New Key

     Open termianak and enter the following command :-

     ```bash
     $ ssh-keygen -t rsa -C "<your email"
     ```

     - Press Enter when prompted to enter a file, this will save the keys to the default location i.e. `~/ssh/id_rsa` 

     - When prompted to enter a password, when you hit enter without typing anything that means `no password`. Which is okay.

     - The output in the `Terminal` should look like this :- 

       ```bash
       Your identification has been saved in id_rsa.
       Your public key has been saved in id_rsa.pub.
       The key fingerprint is:
       SHA256:C3AB8FF13720E8AD9047DD39466B3C8974E592C your@email_address.com
       The key's randomart image is:
       +---[RSA 2048]----+
       | .       =   ..  |
       |o . . o + = ..   |
       | =.o o o o o  .  |
       |+ +o. .  ..  . . |
       |.+E  .  S   o o..|
       |..     .  .o . .+|
       |        o  oo .o+|
       |       . o  ==o.=|
       |        . .+=B=o |
       +----[SHA256]-----+
       ```

       Awesome! You have your `private` and `public` keys saved 🎉

  2. Add the new key to your system

     In your Terminal, run :-

     ```bash
     $ ssh-add ~/.ssh/id_rsa
     ```

  3. Copy `public key` 

     In your terminal run :-

     Note: Never display show your `private key` to the public 🛑

     ```bash
     $ pbcopy < ~/.ssh/id_rsa.pub
     ```

  4. Add key to Github

     - Visit [Github Key Settings](https://github.com/settings/keys)
     - Click on `New SSH key`
     - Paste the key copied in part 3 above (`command + v`) in the `key` section
     - You can choose to add a title or not, based on your preference.
     - Click on `Add SSH key` to save your key to Github

  5. Verify if the configuration worked.

     - In your terminal run :-

       ```bash
       $ ssh -T git@github.com
       ```

     - You will get this prompt,

       ```bash
       The authenticity of host 'github.com (192.30.252.153)'... can't be established.
       RSA key fingerprint is 00:11:22:33:44:55:66:77:88:99:aa:bb:cc:dd:ee:ff.
       Are you sure you want to continue connecting (yes/no)?
       ```

       Type `yes`

     - If successfull, yoy will see :-

       ```bash
       Hi <your_github_username>! You've successfully authenticated, but GitHub does not provide shell access.
       ```

- **Install rbenv**

  To install rbenv on your computer click this link and follow the prompts [Here](https://www.digitalocean.com/community/tutorials/how-to-install-ruby-on-rails-with-rbenv-on-macos)

  Note:

  - Newer MacBooks uses `zsh` not `bash` for shell. 
  - In the link they use `.bash_profile` replace that with `.zshrc` 
  
***M1 Chip Note:***

Both RVM and Rbenv seem to have some installation issues on M1(ARM) chips out of the box. There might be some work around for both of the managers.

The best bet is to go with `chruby` or `frum` . Frum is fast but might have some issues, therefore I recommend `chruby` for now until `rvm` and `rbenv` 
issues are resolved for ARM chips. 

Check your `~/bundle/config` for `BUNDLE_FORCE_RUBY_PLATFORM`. This will force bundler to ignore ARM64 builds, so delete it if present.
  
- **[Install Chruby](https://github.com/postmodern/chruby)**
  - `brew install chruby`
  - `brew install ruby-install`
  - Add this script to `.zshrc` file.
    ```bash
      export HOMEBREW_PREFIX="$(brew --prefix)"
  
      if [[ -r "$HOMEBREW_PREFIX/opt/chruby/share/chruby/chruby.sh" ]]; then
        source "$HOMEBREW_PREFIX/opt/chruby/share/chruby/chruby.sh"
        source "$HOMEBREW_PREFIX/opt/chruby/share/chruby/auto.sh"
      fi
    ```
  - `ruby-install ruby 3.1.2`
  - restart the terminal
  - `chruby` should return 3.1.2
  

- **[Install Frum](https://github.com/TaKO8Ki/frum)**

  Frum works almost like `rbenv`.

  - `brew install frum`
  - `frum install 3.1.2`
  - `frum local 3.1.2`


- **Install NVM**

  To install nvm on your mac, click the link and follow from step 1 - 3 [Here](https://tecadmin.net/install-nvm-macos-with-homebrew/)

  Note:

  - Newer MacBooks uses `zsh` not `bash` for shell. 
  - In the link they use `.bash_profile` replace that with `.zshrc`

- **Install PostgreSQL**

  To install postgresql with home brew use click on the link [Here](https://wiki.postgresql.org/wiki/Homebrew)

## Installations For Productivity

- [Rectangle](https://rectangleapp.com) -> Screen Management
- [Caffeine](https://www.macupdate.com/app/mac/24120/caffeine) (free) can also download Caffeinated on AppStore for a charge. -> Keeps your system running.

