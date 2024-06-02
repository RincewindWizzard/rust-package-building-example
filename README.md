# rust-package-building-example

An example of how to build a Personal Package Archive for Debian APT delivering your rust application.

## Bump version on each commit

You really want to bump your version on every commit to avoid republishing under already known version.
Use a git hook to automatically bump the patch version on each commit.

    cp hooks/pre-commit .git/hooks
    chmod +x .git/hooks/pre-commit

TODO: This should only bump the version if the previous commit's version is identical to the current version in
Cargo.toml. 
