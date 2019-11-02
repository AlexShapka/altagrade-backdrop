# AltaGrade Developer Stack for Backdrop
This repository helps to quickly get Backdrop running on Docksal, with the most useful developer modules enabled by default.

AltaGrade Developer Stack comes with **Drop** (https://github.com/backdrop-contrib/drop) installed by default, a command line utility for Backdrop CMS developers aimed at speeding up your development cycles.

## Requirements

Docksal is a web-development environment based on Docker for macOS, Windows and Ubuntu Linux. Install Docksal per https://docksal.io/installation.

## Installation

- On command line change working directory to projects folder, for example `cd ~/Projects`, and clone the repository:
```
git clone https://github.com/altagrade/altagrade-backdrop.git your-new-project
cd your-new-project
```

- If you prefer the development branch over the stable version, then open the `.docksal/commands/init` file, comment out two lines under STABLE and uncomment the git line under DEVELOPMENT as shown below:
```
# STABLE
# BRANCH=`curl -s "https://api.github.com/repos/backdrop/backdrop/releases/latest" | awk -F '"' '/tag_name/{print $4}'`
# git clone --branch $BRANCH https://github.com/backdrop/backdrop.git docroot
# DEVELOPMENT
git clone https://github.com/backdrop/backdrop.git docroot
```

- Finally, run the installation script:
```
./init
```

- Go to http://your-new-project.docksal/user, login with username `admin`, password `admin` and start working with your new Backdrop website. 

## Docksal tools

- MailHog is a cool way of catching all messages sent out from your website while developing it. To test it just enable the contact module with `b en contact`, send a test message using the http://your-new-project.docksal/contact form and check your MailHog at http://mail.your-new-project.docksal.

- phpMyAdmin is located at http://pma.your-new-project.docksal.

## Commnad line utilities

You can  manage your Backdrop website on command line using:

- Drop (https://github.com/backdrop-contrib/drop)
- Backdrop Console (https://backdropcms.org/project/b) 
- Drush (https://backdropcms.org/project/drush).

## Stack component versions

AltaGrade Development Stack is deployed with the following software versions by default:

- Apache 2.4
- MySQL 5.6
- PHP 7.2

## Developer modules

The following developer modules are installed and enabled by default:

drush -y dl devel && drush -y en devel
drush -y dl demo && drush -y en demo
drush -y dl search_krumo && drush -y en search_krumo
drush -y dl coder_upgrade && drush -y en coder_upgrade

## Trobleshooting

Report all errors and issues on https://github.com/altagrade/altagrade-backdrop/issues.
