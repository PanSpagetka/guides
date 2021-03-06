## Developer Setup

### Install System Packages

#### Fedora 20+

* Install packages

  ```bash
  sudo yum -y install git-all                            # Git and components
  sudo yum -y install memcached                          # Memcached for the session store
  sudo yum -y install postgresql-devel postgresql-server # PostgreSQL Database server and to build 'pg' Gem
  sudo yum -y install libxml2-devel libxslt-devel        # For Nokogiri Gem
  sudo yum -y install gcc-c++                            # For event-machine Gem
  ```

* Enable Memcached

  ```bash
  sudo systemctl enable memcached
  sudo systemctl start memcached
  ```

* Configure PostgreSQL

  ```bash
  sudo passwd postgres <new_password>
  su postgres -c 'initdb -D /var/lib/pgsql/data'
  sudo systemctl enable postgresql
  sudo systemctl start postgresql
  su postgres -c "psql -c \"CREATE ROLE root SUPERUSER LOGIN PASSWORD 'smartvm'\""
  ```

#### Fedora 22+

As per 20+, with the following changes:

* Install packages

  ```bash
  sudo dnf -y install git-all                            # Git and components
  sudo dnf -y install memcached                          # Memcached for the session store
  sudo dnf -y install postgresql-devel postgresql-server # PostgreSQL Database server and to build 'pg' Gem
  sudo dnf -y install libxml2-devel libxslt-devel patch  # For Nokogiri Gem
  sudo dnf -y install gcc-c++                            # For event-machine Gem
  ```

#### Mac

* Install [Homebrew](http://brew.sh/)

  If you do not have Homebrew installed, go to the Homebrew website and install it.

* Install Packages

  ```bash
  brew install git
  brew install memcached
  brew install postgresql
  ```

* Configure PostgreSQL

  ```bash
  # Enable PostgreSQL on boot
  mkdir -p ~/Library/LaunchAgents
  ln -sfv /usr/local/opt/postgresql/*.plist ~/Library/LaunchAgents
  launchctl load ~/Library/LaunchAgents/homebrew.mxcl.postgresql.plist

  psql -c "CREATE ROLE root SUPERUSER LOGIN PASSWORD 'smartvm'"
  ```

### Install Ruby

* Use a Ruby version manager
  * [chruby](https://github.com/postmodern/chruby) and [ruby-install](https://github.com/postmodern/ruby-install)
  * [rvm](http://rvm.io/)
  * [rbenv](https://github.com/sstephenson/rbenv)
* Required Ruby version is 2.2

### Setup Git and Github

* The most reliable authentication mechanism for git uses SSH keys.
  * [SSH Key Setup](https://help.github.com/articles/generating-ssh-keys) Set up a SSH keypair for authentication.  Note: If you enter a passphrase, you will be prompted every time you authenticate with it.
* Github account setup [Account Settings](https://github.com/settings).
  * [Profile](https://github.com/settings/profile): Fill in your personal information, such as your name.
  * [Profile](https://github.com/settings/profile): Optionally set up an avatar at gravatar.com.  When you set up your gravatar, be sure to have an entry for the addresses you plan to use with git / Github.
  * [Emails](https://github.com/settings/emails): Enter your e-mail address and verify it, click the Verify button and follow the instructions.
  * [Notification Center](https://github.com/settings/notifications) / Notification Email / Custom Routing: Change the email address associated with ManageIQ if desired.
  * If you are a member of the ManageIQ organization:
    * Go to [the Members page](https://github.com/ManageIQ?tab=members).
      * Verify you are listed.
      * Optionally click Publicize Membership.
* Fork ManageIQ/manageiq:
  * Go to [ManageIQ/manageiq](https://github.com/ManageIQ/manageiq)
  * Click the Fork button and choose "Fork to \<yourname\>"
* Git configuration and default settings.

  ```bash
  git config --global user.name "Joe Smith"
  git config --global user.email joe.smith@example.com
  git config --global --bool pull.rebase true
  git config --global push.default simple
  ```

  If you need to use git with other email addresses, you can set the local user.email from within the clone using:

  ```bash
  git config user.name "Joe Smith"
  git config user.email joe.smith@example.com
  ```

### Clone the Code

```bash
git clone git@github.com:JoeSmith/manageiq.git # Use "-o my_fork" if you don't want the remote to be named origin
cd manageiq
git remote add upstream git@github.com:ManageIQ/manageiq.git
git fetch upstream
```

You can add other remotes at any time to collaborate with others by running:

```bash
git remote add other_user git@github.com:OtherUser/manageiq.git
git fetch other_user
```

### Get the Rails environment up and running

```bash
gem install bundler -v "~>1.7.4"
bundle install
cp config/database.pg.yml config/database.yml
bundle exec rake evm:db:reset
bundle exec rake db:seed
```

* Now you can start the full application with `bundle exec rake evm:start`.
  You can access it at <IP_ADDRESS>:3000. Default username is `admin` and password `smartvm`
