## OSX || MacOS Clean Install

### Estimated time for competition: 1 - 2 Hours

#### Things Change:

The guide provides some very exact syntax for install 'all the things' at the time of this writing. While I will try to update it as necessary, there is a very real possibility some command or some option will not be present or work the way it once did. No big deal. Just play around a bit, Google around a bit and figure it out a bit. Literally all the information below was derived from goggling `osx install X`.

## Table of Contents:

- General
  - [Start Here](#forward) • [Initial System Settings](#system-settings) • [Software Recommendations](#additional-recommended-applications)

- Languages / Frameworks
  - [HomeBrew](#homebrew) • [Git](#git) • [dotfiles](#dotfiles) • [rbenv](#rbenv) • [Heroku toolbelt](#heroku-toolbelt) • [Rails](#rails) • [NVM](#nvm)

- Applications
  - [iterm](#iterm) • [spectacle](#spectacle) • [Sublime Text 3](#sublimetext-3) • [Chrome](#chrome) • [Firefox](#firefox) • [FlyCut](#flycut) • [Alfred](#alfred)

- Databases
 - [postgres](#postgres) • [sqlite3](#sqlite3) • [mysql](#mysql) • [MongoDB](#mongodb)


## Forward:

I put together this guide to assist young developers in setting up new OSx hardware. It is built to start from a clean installation of OSX El Capitain. Older versions of OSX should work as well. I'm not saying this collection of software tools is the end all greatest, there are lots of options available, but if you need to get up and running you can create this environment and things will be pretty good.

It's geared in such a way as to be non blocking to anyone with a basic experience level in OSX configuration.

**Note:** If you're here because your existing Ruby ENV is mangled these notes don't apply.

It is recommended that you follow the guide Top => Bottom. As with all things programming, **Order Matters**.

You should be comfortable with the command line before starting this tutorial. Read this [Command Line Quick Reference & Tips](http://learntocodewith.me/command-line/unix-command-cheat-sheet/) if you need a refresher.

Additionally, if you are to 'know what you're doing' with your dev environment you should know a bit about how the ```PATH``` variable works. If this term is foreign to you take a minute to read [this article](https://cbednarski.com/articles/understanding-environment-variables-and-the-unix-path/).

This guide denotes terminal entries with the following character combination:
```
=>$
```
The dollar **$** symbol is frequently used in tutorials to denote a terminal entry. Just being extra clear here, because I see this mistake a lot. **Do Not** include the $ when you type out the commands into terminal. Also it's worth noting that your terminal prompt most likely does not look like mine. That's OK too.

  ### Contributing:

  If you feel I've missed something or if you find a pain point I didn't document, *Please [open an issue](https://github.com/bootcoder/ENV_Scratch_Setup/issues).* Feedback always greatly appreciated.

  If you feel have critical updates or just want to contribute in general, *Please fork it, contribute and open a pull request.*

  As to the subject matter itself, if you don't agree in my choice of software that's awesome!

  But for seriouslies, I'm not saying I don't care about or appreciate how much better ```INSERT RANDO SOFTWARE TITLE HERE``` is. I'm just saying I've heard... it's cool. No need to track me down, shake me around and pontificate furiously whilst cycling through the virtues of ```INSERT RANDO SOFTWARE TITLE HERE```.

### B-E-EFFICIENT

When I say open this program or that, the quickest path is usually via *Spotlight*. System wide you can access Spotlight by pressing CMD+Spacebar, then enter the program or file you are searching for.

```
CMD+Spacebar Terminal
```

Will open the terminal application. You'll find it's fuzzy search impressive, needing only a few characters to open popular apps. This advice remains true even though I will instruct you to replace Spotlight with Alfred in this tutorial. If you'd like more thoughts on efficiency as a dev check out [this link](https://github.com/bootcoder/tipsNtricks)

### A note on Passwords:

Your Apple ID and system passwords are most likely different. Be sure to keep both readily available throughout the installation process.

**Apple ID**

![apple-sign-in](apple_id_sign_in.png)

Apple ID can be used to access the App Store as well as sync different devices via iCloud.

**System Password**

![system-password](username_password.jpg)

This is the password you use to login to OSX on the current computer. If you are prompted for a password at the terminal it is asking for the System Password.

---

# Start Installation

### HomeBrew

  Head on over to the [HomeBrew site](https://brew.sh/) and copy the link.

  In the terminal application paste it in: (It probably looks a lot like this)

  ```bash
  =>$ /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
  ```

  This process will prompt you for your system password. Most times in your day to day developer life you want to avoid using SUDO to perform installations. Homebrew is an exception to this rule. Give it root access whenever it asks. Confidence is very high that HomeBrew won't set any permissions incorrectly.

  Homebrew ProTip: Before brewing anything now and in the future, you should first run and resolve,

  ```=>$ brew update```

  ```=>$ brew doctor```

### Git

  1. Install Git via Homebrew
  ``` =>$ brew install git ```

  2. Check Git version
    ``` =>$ git --version ```

  3. Which should return you _something like_
    ``` git version 2.2.2 ```

  4. Set global Git variables. (Fill in the blanks where needed)

    - ``` =>$ git config --global user.name "BLANK (The name you want displayed on Git, could be Username or someName)" ```

    - ``` =>$ git config --global user.email "BLANK (ex: you@example.com) ```

### rbenv

  1. Install rbenv via Homebrew
  ``` =>$ brew install rbenv ```

  2. Check rbenv version to confirm installation.
  ``` =>$ rbenv -v ```

  3. Which should return you _something like_
  ``` rbenv 0.4.0 ```

  4. Check the install versions of Ruby with rbenv.
  ``` =>$ rbenv versions ```

  5. Now install a couple versions of Ruby. This will typically take 5 - 10 minutes a piece. Here are some suggested versions at the time of this writing:
    - ``` =>$ rbenv install 2.3.1 ```
    - ``` =>$ rbenv install 2.0.0-p353 ```

  6. Re-Check the install versions of Ruby with rbenv.
  ``` =>$ rbenv versions ```

  7. Set a Global Ruby version (Can be any version you just installed)
  ``` =>$ rbenv global 2.3.1 ```

### iTerm

  1. Install cask for homebrew
  ``` =>$ brew install cask ```
  2. Install iTerm2
  ``` =>$ brew cask install iterm2 ```
  3. Wait 10 seconds then cmd + spacebar enter iTerm and hit return

##### Base settings

  4. Click preferences
  5. Click the keys tab
  6. Check the box for hotkey in lower left
    - I use ``` cmd + \ ```
  7. Click the profiles tab
  8. Click the sub tab **window**
  9. Slide the transparency slider over to about 20% (the goal is to be able to read text in a browser behind the window but not have it be bright enough to bother you)
  10. Click the sub tab **terminal**, change scroll back lines to 10,000

##### Optional settings

  11. Under the Profiles tab click sub tab **general**
  12. De-select copy to pasteboard on selection ( I don’t want a bunch of terminal commands cluttering up my Flycut)
  13. Click sub tab **colors**
  14. The suggestion here is not to play around too much. The color scheme as it is works pretty well. However, I prefer ``` 00d0fa ``` for the foreground color. But that’s me so...

### dotfiles

  1. From terminal change directory to the desktop.
  ```bash
  =>$ cd ~/Desktop
  ```

  2. Clone Topher's DotFiles onto the desktop.
  ```bash
  =>$ git clone https://github.com/supertopher/dotfiles.git
  ```

  3. Change directories into the repo.
  ```bash
  =>$ cd dotfiles
  ```

  4. Run the script to acquire Bash goodies.
  ```bash
  =>$ ./install
  ```

  5. Restart or open a new terminal tab (CMD+t) to see changes. Any Bash changes will not apply to the current terminal session running.

  6. Go up one level and remove the dotfiles directory
   ```bash
   =>$ cd ..
   =>$ rm -rf dotfiles
   ```

### Spectacle

  1. Install Spectacle via Brew Cask
  ``` =>$ brew cask install spectacle ```
  2. Use ‘spotlight’ to open spectacle for the first time
    - cmd + spacebar to open spotlight
    - type spectacle hit return when you see it auto-populated
  3. Choose open
  4. Choose open system preferences
  5. Click the lock in the lower left
  6. Enter system password
  7. Check the box next to spectacle
  8. Close system prefs
  9. Open Spectacle Preferences
  10. Click the right slider arrow at the bottom
  11. Check ``` Launch Spectacle at login ```

### SublimeText 3

  1. Install Sublime Text 3 via HomeBrew Cask

    - ```brew cask install sublime-text```
    - Provide system password when/if prompted

  2. Install Sublime Text 3 Package Manager

    - In Sublime use ```CMD+Shift+P``` to bring up the command pallet
    - Type ```Install``` and you can select an option for ```Install Package Manager```
    - When finished exit and restart Sublime Text

  3. Install the following packages

  From Sublime do
    1. Use ```CMD+Shift+P``` to open Sublime command fuzzy search
    2. Start typing ```install```, hit enter when you see "Package Control: Install Package"
    3. Start typing the name of the package you want, hit return when you see it.

    - All Autocomplete
    - Better CoffeeScript
    - BracketHighlighter
    - ERB Snippets
    - GitGutter
    - Haml
    - JSX
    - Markdown Preview
    - Package Control
    - PowerCursors
    - SASS
    - SideBarEnhancements
    - sublime-github
    - SublimeLinter
    - SublimeLinter-haml
    - SublimeLinter-ruby
    - TernJS
    - Tomorrow Color Scheme
    - Theme - Tech49

  4. Apply custom user settings (open user settings with ```CMD+Shift+P user```)

  Here is a sample from my editor.

  **Note:** Some of these settings will break Sublime if the corresponding package is not installed first. If you did not install theme || color scheme remove the applicable lines before saving the file.

  **Note:** If your editor goes white and throws an error just set the color from the top bar ```Sublime Text -> preferences -> Color Scheme -> Choose one you like```

  **Note:** The sample below represents the user settings file. Do not simply append this to the bottom of what you have. The settings hash must be 1 complete unit.

  **Note:** Do not edit the Default Settings in Sublime. These will be overwritten whenever Sublime is updated. Always store user settings in.... Preferences: Settings - User.

  ```json
  {
  "atomic_save": false,
  "bold_folder_labels": true,
  "caret_style": "phase",
  "color_scheme": "Packages/User/SublimeLinter/Tomorrow-Night (SL).tmTheme",
  "draw_white_space": "selection",
  "ensure_newline_at_eof_on_save": true,
  "fade_fold_buttons": false,
  "font_face": "Inconsolata",
  "font_size": 17,
  "highlight_line": true,
  "ignored_packages":
  [
    "Emmet",
    "PlainTasks",
    "RubyTest",
    "Theme - Farzher",
    "Vintage"
  ],
  "line_padding_bottom": 1,
  "line_padding_top": 1,
  "rulers":
  [
    80
  ],
  "save_on_focus_lost": true,
  "spell_check": true,
  "tab_size": 2,
  "theme": "Tech49.sublime-theme",
  "translate_tabs_to_spaces": true,
  "trim_trailing_white_space_on_save": true
  }
  ```

  5. Check sublime to confirm installation.
  In iTerm ``` =>$ subl . ```

  This should open a sublime window for the current directory.

### Heroku toolbelt

  1. Install heroku toolbelt vai homebrew
  ``` =>$ brew install heroku-toolbelt ```

  2. Check heroku version to confirm installation.
  ``` =>$ heroku --version ```

  3. Which should return _something like_
  ```bash
  heroku-toolbelt/3.42.45 (x86_64-darwin10.8.0) ruby/1.9.3
  heroku-cli/4.29.0-cac96d9 (amd64-darwin) go1.6
  === Installed Plugins
  heroku-apps@1.7.3
  heroku-cli-addons@0.3.0
  heroku-fork@4.1.1
  heroku-git@2.4.5
  ```

  4. Login to the Heroku CLI Toolkit now using
  ```
  =>$ heroku login
  ```

  You should see something like this. Note the email and password are specifically your Heroku email and password.

  ```
  Enter your Heroku credentials.
  Email: adam@example.com
  Password (typing will be hidden):
  Authentication successful.
  ```
### NVM

  1. Install [NVM](https://github.com/creationix/nvm)
    ```=>$ curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.33.2/install.sh | bash```
  2. Close & restart your terminal

  3. Install Node
    ```nvm install node```
  4. Check node version to confirm installation.
    ```=>$ node -v```

  5. Which should return _something like_
    ```v4.1.1```

  6. Check NPM version to confirm installation.
    ```=>$ npm -v```

  7. Which should return _something like_
    ```2.14.4```

### postgres

  1. Install Postgresql via Homebrew.
  ``` =>$ brew install postgres ```

  2. Start the Postgresql server.

  Notice the messages displayed after completion. Typical OK 200 in Bash is nothing at all. When things go well Bash doesn't tell you about it. That said, when a developer cares enough to put in some extra text after the script runs, you should care enough to read it... Post install here will most likely contain this line:

  ```bash
    =>$ brew services start postgresql
  ```

  Go ahead and run that to have brew start up postgres.

  3. Check postgresql version to confirm installation.
  ``` =>$ psql --version ```

  4. Which should return _something like_
  ``` psql (PostgreSQL) 9.4.0 ```

### sqlite3

  1. Install sqlite3 via Homebrew
  ``` =>$ brew install sqlite ```

  2. Check sqlite3 version to confirm installation.
  ``` =>$ sqlite3 --version ```

  3. Which should return _something like_
  ``` 3.8.5 2014-08-15 22:37:57 c8ade949d4a2eb3bba4702a4a0e17b405e9b6ace ```

### mysql

  1. Install mysql via Homebrew
  ``` =>$ brew install mysql ```

  2. Start the mysql server
  ```bash
  =>$ ln -sfv /usr/local/opt/mysql/*.plist ~/Library/LaunchAgents

  =>$ launchctl load ~/Library/LaunchAgents/homebrew.mxcl.mysql.plist
  ```

  2. Check mysql version to confirm installation.
  ``` =>$ mysql --version ```

  3. Which should return _something like_
  ``` mysql  Ver 14.14 Distrib 5.7.11, for osx10.10 (x86_64) using  EditLine wrapper ```

### MongoDB

  1. Install MongoDB via Homebrew
  ``` =>$ brew install mongodb --with-openssl ```

  2. Check Mongo version to confirm installation.
  ``` =>$ mongo —version ```
  ```bash
  To have launchd start mongodb now and restart at login:
  brew services start mongodb
Or, if you don't want/need a background service you can just run:
  mongod --config /usr/local/etc/mongod.conf
  ```

  3. Which should return _something like_
  ``` MongoDB shell version: 3.0.4 ```

### Rails

  1. Install Rails via Gem
  ``` =>$ gem install rails ```

  2. Check Rails version to confirm installation.
  ``` =>$ rails —v ```

  3. Which should return _something like_
  ``` Rails 4.2.6 ```

  ProTip: Don't ever EVER use sudo to install a GEM. IDC what the internet tells you. If you are using sudo to install a GEM you are doing it WRONG.

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

  1. Install via HomeBrew Cask with ```=>$ brew cask install flycut```
  2. Open Flycut
  3. Click the red flycut icon in the menu bar
  4. Choose preferences
  5. Under general select launch @ login
  6. Reduce remember amount from 40 to 20
  7. Under appearance tab, set all three values down the middle

### Alfred

  1. Download [Alfred](https://www.alfredapp.com)
  2. Open finder
  3. Go to downloads
  4. Drag the Alfred app into the applications folder
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
  9. Disable Spotlight indexing to improve performance.
    - Open Alfred ``` cmd + spacebar ```
    - Enter ``` spotlight ``` to open spotlight preferences
    - Under the 'Search Results' tab, disable all options
    - Disable 'Allow Spotlight Suggestions in Spotlight and Look up'


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

### System Settings

Now that you're all installed and whatnot. Here are some recommended setting to apply to your machine.

- Right-click the battery in the menu bar. Toggle on ``` Show Percentage ```
- Right-click the vertical bar in the Dock. Toggle ``` automatically hide Dock ```
- Set global no ri no rdoc
```bash
 =>$ echo "gem: --no-ri --no-rdoc" >> ~/.gemrc
```
- Set global rspec settings
```bash
=>$ echo $'--color\n--tty\n--format documentation' >> ~/.rspec
```

## Additional Recommended Applications

Terminal Apps

- ``` =>$ brew install hub ``` -- Extended Git commands in terminal.
- ``` =>$ brew install imagemagick ``` -- Super awesome gem for dealing with image files.
- ``` =>$ brew install tree ``` -- Nice way to display tree structure of a directory in terminal.

OSX Apps

- [VLC](http://www.videolan.org/vlc/index.html) -- Best media player out there for like a decade now.
- [Dash](https://kapeli.com/dash) -- Great documentation and snippet management software.
- [Postman](https://www.getpostman.com/) -- Simple easy API exploration tool.
- [Private Internet Access](https://www.privateinternetaccess.com/) -- Best $40.00 I spend all year EVERY YEAR. Secure INTERNET connection from anywhere as well as an easy bypass to geographical restrictions. Moral of the story: I can do banking stuff from open WIFI in Starbucks while streaming a soccer match that is in blackout anywhere outside of the UK. All with 0 worries.
- [f.lux](https://justgetflux.com/) -- Adjusts the chroma setting of your display based on the time of day.
- [Dropbox](https://www.dropbox.com/) -- Every line of code I've ever written resides in my dropbox. Moral of the story: I can throw my laptop out the window and give 0 cares.
- Chrome Extensions
  - colorzilla -- Helpful color picker.
  - currently -- Nice new tab page, clean and useful
  - jsonview -- Returning json from some page, why not have it look decent....
  - web-developer -- Collection of dev tools to help.
  - One Tab -- Collapse all tabs down into a single tab that lists them out in a shareable format. Does not retain active session. Since each tab is a separate process this can be a HUGE memory saver. Best extension ever.
  - Tab Scissors -- Use in conjunction with OneTab. Tab scissors takes everything from the right of the current tab and opens it in a new window, removing it from the current window. Super useful.

----

### Contributing:

If you feel I've missed something or if you find a pain point I didn't document, *Please [open an issue](https://github.com/bootcoder/ENV_Scratch_Setup/issues).* Feedback always greatly appreciated.

If you have critical updates or just want to contribute in general, *Please fork it, contribute and open a pull request.*

As to the subject matter itself, if you don't agree in my choice of software that's awesome!

But for seriouslies, I'm not saying I don't care about or appreciate how much better ```INSERT RANDO SOFTWARE TITLE HERE``` is. I'm just saying I've heard... it's cool. No need to track me down, shake me around and pontificate furiously whilst cycling through the virtues of ```INSERT RANDO SOFTWARE TITLE HERE```.

### Fin

Thanks for stopping by. Hope this helped. Happy Hacking,

BootCoder
