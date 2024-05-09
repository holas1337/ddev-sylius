# General information
DDEV boilerplate code for quick Sylius setup.

Please treat is as an early alpha - version 0.1.

# Local setup

```bash
rm -r .git
ddev start
ddev sylius-install
```

Run backup so you can easily restore it later
```bash
ddev backup
```

## Build from backup
Build the project
```bash
ddev build-site
```

or rebuild without touching DB and Media
```bash
ddev rebuild-site
```

## Commands

### ddev
```bash
ddev cc                 # clear all cache (Symfony and Doctrine)
ddev dist               # install Sylius assets, install yarn assets and build them
ddev security-checker   # check for security issues in packages
ddev backup             # backup database and media
ddev database-import    # import database
ddev files-import       # import media
ddev code-check         # run Coding standards checks
```

### Composer
```bash
ddev composer <params>
```

### Symfony
```bash
ddev exec bin/console <COMMAND>
ddev exec bin/console about                                           # show Symfony about information
ddev exec bin/console doctrine:migrations:migrate                     # run all migrations
ddev exec bin/console doctrine:migrations:diff                        # create new migration
```

### Yarn
```bash
ddev yarn <param>
ddev yarn install                                                     # install all dependencies
ddev yarn build                                                       # build assets
ddev yarn watch                                                       # watch assets
```

# Xdebug
enable in .ddev
```bash
ddev xdebug on
```

## PHPStorm
When asked for mapping choose 
```bash
/var/www/html/index.php
```

If something is not working check if mappings `Settings \ PHP \ Servers` look like this:
```
project_dir (first folder in Project Files) -> /var/www/html
prokect_dir/public                          -> /var/www/html/public
```

```
host: sylius.ddev.site    # this might be different if you changed `.ddev/config` `name` or using additional hosts
port: 8443
```
And now it should work
