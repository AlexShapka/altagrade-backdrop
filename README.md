# AltaGrade Developer Stack for Backdrop
This repository helps to quickly get Backdrop running on Docksal, with the most useful developer modules enabled by default.

AltaGrade Developer Stack comes with **Brush** (https://github.com/backdrop-contrib/brush) installed by default, a command line utility for Backdrop CMS developers aimed at speeding up your development cycles.

## Requirements

Docksal is a web-development environment based on Docker for macOS, Windows and Ubuntu Linux. Install Docksal per https://docksal.io/installation.

## Installation

- On command line change the working directory to your Docksal's projects folder, for example `cd ~/Projects`, and clone the repository:
```
git clone https://github.com/altagrade/altagrade-backdrop.git your-new-project
cd your-new-project
./init
```

- If you prefer the stable branch over the develpment version, then before running the `./init` command above, open the `.docksal/commands/init` file, uncomment two lines under STABLE and comment out the git line under DEVELOPMENT as shown below:
```
# STABLE
# BRANCH=`curl -s "https://api.github.com/repos/backdrop/backdrop/releases/latest" | awk -F '"' '/tag_name/{print $4}'`
# git clone --branch $BRANCH https://github.com/backdrop/backdrop.git docroot
# DEVELOPMENT
git clone https://github.com/backdrop/backdrop.git docroot
```

- Go to http://your-new-project.docksal/user, login with username `admin`, password `admin` and start working with your new Backdrop website. 

## Docksal tools

- MailHog is a cool way of catching all messages sent out from your website while developing it. To test it just enable the contact module with `drop en contact`, send a test message using the http://your-new-project.docksal/contact form and check your MailHog at http://mail.your-new-project.docksal.

- phpMyAdmin is located at http://pma.your-new-project.docksal.

## Command line utilities

You can  manage your Backdrop website on command line using:

- Brush (https://github.com/backdrop-contrib/brush)
- Backdrop Console (https://backdropcms.org/project/b) 
- Drush (https://backdropcms.org/project/drush).

## Stack component versions

AltaGrade Development Stack is deployed with the following software versions by default:

- Apache 2.4
- MySQL 5.6
- PHP 7.2

## Developer modules

The following developer modules are installed and enabled by default:

- Devel 
- Demo 
- Search Krumo 
- Coder Upgrade 
- Coder Review

## Additional modules

The following modules are downloaded and recommended for production sites:

- Remove Generator
- Honeypot
- Session Limit
- Passphrase Policy
- Autologout

## Trobleshooting

Report all errors and issues on https://github.com/altagrade/altagrade-backdrop/issues
