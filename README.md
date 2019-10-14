# AltaGrade Development Stack for Backdrop
This repository helps to quickly get the latest development branch of Backdrop running on Docksal.

## Installation

- Install Docksal per https://docksal.io/installation if you haven't already done it.

- Go to your ~/Projects, clone the repository and run the installation script:
```
git clone git@github.com:AlexShapka/altagrade-backdrop.git your-new-project
cd your-new-project
```

- If you prefer stable version over the development branch, then open the `.docksal/commands/init` file, comment out the `git clone https://github.com/backdrop/backdrop.git docroot` line and uncomment two lines just after it like so:

```
# git clone https://github.com/backdrop/backdrop.git docroot
STABLE=`curl -s "https://api.github.com/repos/backdrop/backdrop/releases/latest" | awk -F '"' '/tag_name/{print $4}'`
git clone --branch $STABLE https://github.com/backdrop/backdrop.git docroot
```

- Finally, run the installation scipt:
```
./init
```

- Go to http://your-new-project.docksal/user, login with username `admin`, password `admin` and start working with your website.

## Additional plugins

- MailHog is a cool way of catching all messages sent out from your website while developing it. To test it just enable the contact module with `drush en contact`, send a test message using the http://your-new-project.docksal/contact form and check your MailHog at http://mail.your-new-project.docksal.

- phpMyAdmin is located at http://pma.your-new-project.docksal.

## Versions

**AltaGrade Development Stack** is deployed with the following software versions by default:

- Apache 2.4
- MySQL 5.6
- PHP 7.2

## Trobleshooting

Report all errors and issues on https://github.com/AlexShapka/altagrade-backdrop/issues.
