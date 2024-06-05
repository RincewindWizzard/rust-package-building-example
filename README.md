# rust-package-building-example

An example of how to build a Personal Package Archive for Debian APT delivering your rust application.
Includes [Github Actions](.github/workflows(rust_deb.yml) for CI/CD.
Builds your documentation using [Mkdocs](https://www.mkdocs.org/).

## Installing from PPA

    apt update && apt upgrade -y && apt install -y curl wget gpg
    wget -O- https://rincewindwizzard.github.io/rust-package-building-example/deb/KEY.gpg | gpg --dearmor > /etc/apt/trusted.gpg.d/rust-package-building-example.gpg
    echo "deb [arch=amd64,signed-by=/etc/apt/trusted.gpg.d/rust-package-building-example.gpg]  https://rincewindwizzard.github.io/rust-package-building-example/deb/ ./" > /etc/apt/sources.list.d/rust-package-building-example.list
    apt update
    apt install rust-package-building-example

## Bump version on each commit

You really want to bump your version on every commit to avoid republishing under already known version.
Use a git hook to automatically bump the patch version on each commit.

    cp hooks/pre-commit .git/hooks
    chmod +x .git/hooks/pre-commit

TODO: This should only bump the version if the previous commit's version is identical to the current version in
Cargo.toml. 
