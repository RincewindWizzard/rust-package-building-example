# Rust package building exmple

This is an opinionated example template on how to distribute you own rust application to the masses.
It builds your project with cargo and creates a debian archive and a PPA to add to your sources lists.
It also builds your mkdocs documentation. Everything is hosted on github pages without further costs.

## Installing from PPA

    apt update && apt upgrade -y && apt install -y curl wget gpg
    wget -O- https://rincewindwizzard.github.io/rust-package-building-example/deb/KEY.gpg | gpg --dearmor > /etc/apt/trusted.gpg.d/rust-package-building-example.gpg
    echo "deb [arch=amd64,signed-by=/etc/apt/trusted.gpg.d/rust-package-building-example.gpg]  https://rincewindwizzard.github.io/rust-package-building-example/deb/ ./" > /etc/apt/sources.list.d/rust-package-building-example.list
    apt update
    apt install rust-package-building-example


