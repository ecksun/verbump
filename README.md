This is a small bash-script that bumps the version of a project.

How the version is stored is dependent on the type of project.

# installation

```bash
    # install dependencies
    npm install -g semver

    # download script
    # some distributions will automatically add ~/bin to path if it exists, debian
    # is one of them
    mkdir -p ~/bin
    wget https://gitlab.com/ecksun/verbump/raw/master/verbump -O ~/bin/verbump
    chmod +x ~/bin/verbump
```

## runtime dependencies

* semver
* npm (only required for npm projects)

# How it works

1. Update version in whatever storage format is apropriate
2. Commit change with version as message
3. tag commit with an annotated tag

# Supported project formats

| repository type | file         | change                                 |
| ---             | ---          | ---                                    |
| sbt             | build.sbt    | Change the line matching `version := ` |
| npm             | package.json | delegate to `npm version`              |
