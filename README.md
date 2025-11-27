# General information
DDEV boilerplate code for quick Sylius setup.

Please treat is as an early alpha - version 0.1.

# Local setup

```bash
ddev start
ddev sylius-install
```

Run backup so you can easily restore it later
```bash
ddev backup
```

## Cleanup and start over
```bash
ddev sylius-cleanup
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

## Start a new project using this boilerplate
Adjust the name of the project in .ddev/config.yaml file, then run:
```bash
ddev start
ddev sylius-install
rm -rf .git
git init
git add .
git commit -m "Initial commit"
```

Set remote, push code....

Additionally, you can remove DDEV commands
- .ddev/commands/host/sylius-install
- .ddev/commands/host/sylius-cleanup
They are useful only for initial setup.

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


# Additional information

## Compatibility
This boilerplate was tested on:
- Windows 11 with WSL2 (Ubuntu 24.04) + Docker Desktop
- [To Do] macOS Tahoe (Apple Silicon) + Docker Desktop 

Should work without a problem on Linux with Docker as well.

## [To Do] macOS specifics
Need to properly set
- `upload_dirs` in .ddev/config.yaml to avoid issues with media uploads
- mutagen ignore sync for better performance
