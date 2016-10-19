# computer-config

## OS-X

Set up for a clean OS-X laptop.  I did not make a script as my
requirements vary.

- [shift it](https://github.com/fikovnik/ShiftIt),
[direct download](https://github-cloud.s3.amazonaws.com/releases/959084/72c0dcfa-ed3a-11e4-9d8e-cdafe2ee6e57.zip?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAISTNZFOVBIJMK3TQ%2F20161017%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20161017T032321Z&X-Amz-Expires=300&X-Amz-Signature=0e424ba996d4c7741aae86884b8347d77d521de04e91d432a40679c63695ee3f&X-Amz-SignedHeaders=host&actor_id=0&response-content-disposition=attachment%3B%20filename%3DShiftIt-1.6.3.zip&response-content-type=application%2Foctet-stream): Tool to move
windows side by side etc, similar to
WindowKey Left etc on Windows.
- [FlyCut](https://github.com/TermiT/Flycut/), [direct download](https://github-cloud.s3.amazonaws.com/releases/1502462/41c4d70e-88ad-11e6-8f6c-c51f67052c84.zip?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAISTNZFOVBIJMK3TQ%2F20161017%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20161017T032705Z&X-Amz-Expires=300&X-Amz-Signature=b167e10e4a3bfd6f873f73e805da7dc2ff5b34ad2ae7effd5ba44a067edc1ca7&X-Amz-SignedHeaders=host&actor_id=0&response-content-disposition=attachment%3B%20filename%3DFlycut.app.1.8.1.zip&response-content-type=application%2Foctet-stream) Cut and paste memory tool

```
Preferences
stickey bezel
launch flycut on login
```

- [Iterm2](https://iterm2.com/),  [direct download](https://iterm2.com/downloads/stable/iTerm2-3_0_10.zip) is a terminal replacement 

- [Aquamacs](http://aquamacs.org/), [direct download](https://github-cloud.s3.amazonaws.com/releases/163782/df98aa78-7ec1-11e6-94e2-f2baf22a8138.dmg?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAISTNZFOVBIJMK3TQ%2F20161017%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20161017T033114Z&X-Amz-Expires=300&X-Amz-Signature=2852372ae195be018fcafa83540533b2ccf160788a97b283e5e356ea6a2dcb6a&X-Amz-SignedHeaders=host&actor_id=0&response-content-disposition=attachment%3B%20filename%3DAquamacs-Emacs-3.3.dmg&response-content-type=application%2Foctet-stream)

- install IntelliJ (get it via an airdrop from someone who has the install package)
	- plugins:
		- NodeJS
		- Karma
		- Line Sorter
		- Angular JS

- install brew via commandline in your iterm2
```
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
brew install markdown
brew install ruby
brew install gem
gem install compass
brew install node
```
  need this version since it gives you access to npm, the node4 version does not have npm
```
brew install joe

npm -g install grunt-cli
npm -g install karma
npm -g install bower
npm -g install phantomjs
```
go to the project directory (~/workspace/farmer-css)
```
npm install (gets grunt and bower)
grunt update
```
optionally, get the node directory from a working machine and airdrop it to whomever needs it.

if grunt update fails then try:
```
bower install
cd test/e2e
npm install
```
look for any errors such as the following example
```
> node node_modules/protractor/bin/webdriver-manager update

events.js:141
      throw er; // Unhandled 'error' event
      ^

Error: unable to get local issuer certificate
    at Error (native)
    at TLSSocket.<anonymous> (_tls_wrap.js:1022:38)
    at emitNone (events.js:67:13)
    at TLSSocket.emit (events.js:166:7)
    at TLSSocket._init.ssl.onclienthello.ssl.oncertcb.TLSSocket._finishInit (_tls_wrap.js:586:8)
    at TLSWrap.ssl.onclienthello.ssl.oncertcb.ssl.onnewsession.ssl.onhandshakedone (_tls_wrap.js:428:38)

npm ERR! Darwin 15.6.0
npm ERR! argv "/usr/local/Cellar/node4-lts/4.6.0/bin/node" "/usr/local/bin/npm" "install"
npm ERR! node v4.6.0
npm ERR! npm  v2.15.9
npm ERR! code ELIFECYCLE
npm ERR! @ install: `node node_modules/protractor/bin/webdriver-manager update`
npm ERR! Exit status 1
npm ERR!
```
or go to starbucks and rerun `grunt update` in the farmers-css directory


install mongo
```
brew install mongodb
```

brew unlink node ( vice versa is brew link node4-lts)
brew install node `brew install homebrew/versions/node4-lts`

- node updates


sample ~/.git-authors
```
authors:
  jl: Joey Leung
  bk: Ben Kamysz
  ap: Addison Pan
  hs: Harshesh Shah
  mh: Manuk Hovanesian

email_addresses:
  jl: joey.leung@farmersinsurance.com
  bk: benjamin.kamysz@farmersinsurance.com
  ap: addison.pan@farmersinsurance.com
  hs: harshesh.shah@capgemini.com
  mh: manuk.hovanesian@farmersinsurance.com
```
sample ~/.gitconfig:
```
    [user]
        name = Addison Pan
        email = haha@hehe.there

    [alias]
      co = checkout
      ci = commit
      st = status
      hist = log --pretty=format:\"%h %ad | %s%d [%an]\" --graph --date=short
      type = cat-file -t
      dump = cat-file -p
      lola = log --graph --decorate --pretty=oneline --abbrev-commit --all
      lola9 = log --graph --decorate --pretty=oneline --abbrev-commit -n9
      cb = rev-parse --abbrev-ref HEAD
      dci = duet-commit
      pl = pull --ff-only
      unpushed = log --branches --not --remotes --simplify-by-decoration --decorate --oneline
      ready = rebase -i @{u}
      lg = log --color --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr)%C(bold blue)<%an>%Creset' --abbrev-commit
      story = "!f() { n=$1; story=$(sed -e \"s/#//\" <<< $n); branch=$(git branch -a | grep -o \"$story[-_a-zA-Z]*\" | head -n 1); git checkout $branch; }; f"

    [core]
      editor = /usr/bin/nano
      excludesfile = /Users/addison.pan/.gitignore_global
      autocrlf = input

    [difftool "sourcetree"]
      cmd = opendiff \"$LOCAL\" \"$REMOTE\"
      path =
    [mergetool "sourcetree"]
      cmd = /Users/addison.pan/Applications/SourceTree.app/Contents/Resources/opendiff-w.sh \"$LOCAL\" \"$REMOTE\" -ancestor \"$BASE\" -merge \"$MERGED\"
      trustExitCode = true
    [mergetool "bc3"]
      cmd = \"/Users/addison.pan/Applications/Beyond Compare.app/Contents/MacOS/bcomp\"  \"$LOCAL\" \"$REMOTE\" -ancestor \"$BASE\" -merge \"$MERGED\"
      trustExitCode = true

    [merge]
      tool=bc3
```

OS setup
System Preference -> Advanced -> Proxies -> click first 2 (Auto Proxy Discovery, Automatic Proxy Configuration)

bashit
installation directions: `https://github.com/Bash-it/bash-it`
```
$ . ~/.bash_profile
```

MONGO setup/requirements/start
```
sudo mkdir -p /data/db
sudo chmod 755 /data/db
sudo chown -R addison.pan: /data
mongod &
```
test with `mongo`


- need to install ant 'brew install ant'
	- require java 'brew cask install java' 
- need to install selenium 



for remote pairing:
screen hero
	- request an invite from a member who already has an account

note: all bottle files that were downloaded
~/Libarary/Cache

Airdrop - visible hostname
```
scutil --set HostName
```

Git Duet Wrapper
```
brew tap git-duet/tap
brew install git-duet
```
Then use the git duet wrapper by setting it up as the git executable in intelliJ.  The git duet wrapper is under scripts/intellij_git_duet_wrapper.sh
TO DO:
setup proxies for npm and grunt 
