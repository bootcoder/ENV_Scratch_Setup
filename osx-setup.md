## El Capitain Fresh Install

### HomeBrew

  Following this [guide](https://coolestguidesontheplanet.com/installing-homebrew-on-os-x-el-capitan-10-11-package-manager-for-unix-apps/
):

  1. Install Xcode from the App Store (This will take A WHILE)

  2. Open terminal run ```xcode-select --install```
    - Follow the prompts
    - When finished open Xcode
    - Agree to the license, enter your password, wait until the welcome screen comes up, then exit Xcode.

  3. Install Homebrew with Curl.

    ``` ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)" ```

  Homebrew ProTip: Before brewing ANYTHING you should first run and resolve,

    ``` brew update ```

    ``` brew doctor ```

### Git

  1. Install Git via Homebrew
  ``` brew install git ```

  2. Check Git version
    ``` git --version ```

  3. Which should return you something like
    ``` git version 2.2.2 ```

  4. Set global Git variables. (Fill in the blanks where needed)

    - ``` git config --global user.name "Your Name" ```

    - ``` git config --global user.email you@example.com ```


### dotfiles

  **Bold == Notes**

  **update with sublime, bash, gitconfig**

  **update spec with documentation**

  **update for sublime 3**

  1. From terminal change directory to the desktop.

  2. Clone Topher's DotFiles onto the desktop.
  ``` git clone https://github.com/supertopher/dotfiles.git ```

  3. Change directories into the repo.
  ``` cd dotfiles ```

  4. Run the script to acquire goodies.
  ``` ./install ```

  5. Restart terminal to see changes.

### rbenv

  1. Install rbenv via Homebrew
  ``` brew install rbenv ```

  2. Check rbenv version to confirm installation.
  ``` rbenv -v ```

  3. Which should return you something like
  ``` rbenv 0.4.0 ```

  4. Check the install versions of Ruby with rbenv.
  ``` rbenv --versions ```

  5. Now install a couple versions of Ruby. Here are some suggestions, you do you boo.
    - ``` rbenv install 2.2.1 ```
    - ``` rbenv install 2.0.0-p353 ```
    - ``` rbenv install 2.1.2 ```
    - ``` rbenv install 1.9.3-p551 ```


### Node - NPM

  1. Install Node via Homebrew
    ``` brew install node ```
  2. Check node version to confirm installation.
    ``` node -v ```

  3. Which should return something like
    ``` v4.1.1 ```

  4. Check NPM version to confirm installation.
    ``` npm -v ```

  5. Which should return something like
    ``` 2.14.4 ```

### SublimeText 3
  1. Install Sublime Text 3 via Homebrew

  - ```brew install caskroom/cask/brew-cask```
  - ```brew tap caskroom/versions```
  - ```brew cask install sublime-text3```
  - Provide system password when prompted

### heroku toolbelt
  1. Install heroku toolbelt vai homebrew
  ``` brew install heroku-toolbelt ```

  2. Check heroku version to confirm installation.
  ``` heroku --version ```

  3. Which should return something like
  ```bash
  heroku-toolbelt/3.42.45 (x86_64-darwin10.8.0) ruby/1.9.3
  heroku-cli/4.29.0-cac96d9 (amd64-darwin) go1.6
  === Installed Plugins
  heroku-apps@1.7.3
  heroku-cli-addons@0.3.0
  heroku-fork@4.1.1
  heroku-git@2.4.5
  ```

### iterm 3
  1. Download [iterm 3](https://www.iterm2.com/version3.html)
  2. Open finder
  3. Go to downloads
  4. Drag the iterm app into the applications folder on the sidebar
  5. Now open the applications folder grab the iterm app and drag it to your dock at the bottom of the screen.
  6. cmd + spacebar enter iterm and hit return
  7. Choose open
  8. Click iterm in the top left corner dropdown.

##### Base settings

  9. Click preferences
  10. Click the keys tab
  11. Check the box for hotkey in lower left
    - I use ``` cmd + \ ```
  12. Click the profiles tab
  13. Click the window sub tab
  14. Slide the transparency slider over to about 20% (the goal is to be able to read text in a browser behind the window but not have it be bright enough to bother you)
  15. Click the sub tab terminal, change scroll back lines to 10,000

##### Optional settings

  16. Click sub tab general
  17. Deselect copy to pasteboard on selection ( I don’t want a bunch of terminal commands cluttering up my flycut)
  18 . Click sub tab colors
  19. The suggestion here is not to play around too much. The color scheme as it is works pretty well. However, I prefer ``` 00d0fa ``` for the foreground color. But that’s me so...

### Spectacle
  1. Download [Spectacle](https://www.spectacleapp.com/)
  2. Open finder
  3. Go to downloads
  4. Drag the Spectacle app into the applications folder
  5. Use ‘spotlight’ to open spectacle for the first time
    - cmd + spacebar to open spotlight
    - type spectacle hit return when you see it autopopulated
  6. Choose open
  7. Choose open system preferences
  8. Click the lock in the lower left
  9. Enter system password
  10. Check the box next to spectacle
  11. Close system prefs

### postgres

  1. Install Postgresql via Homebrew.
  ``` brew install postgres ```

  2. Start the Postgresql server.

  Notice the messages displayed after completion. When a developer cares enough to put in some extra text after the script runs, you should care enough to read it...

  ```bash
  To have launchd start postgresql at login:
  mkdir -p ~/Library/LaunchAgents
  ln -sfv /usr/local/opt/postgresql/*.plist ~/Library/LaunchAgents
  Then to load postgresql now:
  launchctl load ~/Library/LaunchAgents/homebrew.mxcl.postgresql.plist
  ```

  Run these commands to setup autostart for postgres.

  3. Check postgresql version to confirm installation.
  ``` psql --version ```

  4. Which should return something like
  ``` psql (PostgreSQL) 9.4.0 ```

### sqlite3

  1. Install sqlite3 via Homebrew
  ``` brew install sqlite ```

  2. Check sqlite3 version to confirm installation.
  ``` sqlite3 --version ```

  3. Which should return something like
  ``` 3.8.5 2014-08-15 22:37:57 c8ade949d4a2eb3bba4702a4a0e17b405e9b6ace ```

### mysql

  1. Install mysql via Homebrew
  ``` brew install mysql ```

  2. Start the mysql server
  ```bash
  ln -sfv /usr/local/opt/mysql/*.plist ~/Library/LaunchAgents

  launchctl load ~/Library/LaunchAgents/homebrew.mxcl.mysql.plist

  ```

  2. Check mysql version to confirm installation.
  ``` mysql --version ```

  3. Which should return something like
  ``` mysql  Ver 14.14 Distrib 5.7.11, for osx10.10 (x86_64) using  EditLine wrapper ```

### MongoDB

  1. Install MongoDB via Homebrew
  ``` brew install mongodb --with-openssl ```

  2. Check Mongo version to confirm installation.
  ``` mongo —version ```

  3. Which should return something like
  ``` MongoDB shell version: 3.0.4 ```

### Rails

### Chrome
  1. Download [Chrome](https://www.google.com/chrome/browser/desktop/)
  2. Open downloads in finder
  3. Run the .dmg installer
  4. Drag into provided applications folder

### Firefox
  1. Download [Firefox](https://www.mozilla.org/en-US/firefox/new/)
  2. Open downloads in finder
  3. Run the .dmg installer
  4. Drag into applications folder

### Flycut
  1. Download from app store
  2. Open Flycut
  3. Click the red flycut icon in the menu bar
  4. Choose preferences
  5. Under general select launch @ login
  6. Reduce remember amount from 40 to 20
  7. Under hotkey tab, set to ``` cmd + cntr + / ```
  8. Under appearance tab, set all three values down the middle

### Alfred 2
  1. Download [Alfred 2](https://cachefly.alfredapp.com/Alfred_2.8.3_435.zip)
  2. Open finder
  3. Go to downloads
  4. Drag the Alfred 2 app into the applications folder
  5. Use spotlight to open Alfred
  6. Choose open
  7. Choose OK to access contacts
  8. Now we are going to disable spotlight and reassign ``` cmd + spacebar ``` to Alfred
    - Use spotlight (cmd+spacebar) to open spotlight :-)
    - In the lower left corner of the system preferences pane choose keyboard shortcuts
    - Deselect the top option to disassociate spotlight with the cmd + space keys
    - Now close spotlight settings
    - Click back or reopen alfred settings
    - Set Alfred hotkey to cmd+Space under Alfred preferences

#### Settings
  1. Set your location to the United States
  2. Appearance tab
    - Theme sub tab
      - Theme set to dark and smooth
    - Large type subtab
      - Change the dropdown to ‘Fill the screen’
    - Options subtab
      - Toggle hide hat on Alfred window
      - Toggle hide menu bar icon

## Additional Recommended Applications

- Private Internet Access
- Flux
- Dropbox

