# rust-hello-world
Getting started with Rust development.

## Windows
Need to install [Microsoft C++ Build Tools](https://visualstudio.microsoft.com/visual-cpp-build-tools/)

Reccomended to select **.NET desktop development**, **Desktop development with C++**, and **Universal Windows Platform development**. I think only **Desktop development with C++** is necessary if you're developing cross-platform, but I'm not sure.

Then install [Rust](https://www.rust-lang.org/tools/install). It should recognize you're on Windows and point you to the Windows installers.

*Note: You can also install Rust for Linux under WSL, but for this I'm going to be looking into native Windows development to see how easy it is to develop cross-platform.*

Run `cargo init` to initialize the Rust project in the current directory, or `cargo new <dir>` to create a new project in a new directory.

Read the boilerplate `.gitignore` from GitHub - since we're compiling an executable, we want to comment out the `Cargo.lock` so that it gets included in the repo. If we were compiling a library, we wouldn't want to include it. More info [here](https://doc.rust-lang.org/cargo/guide/cargo-toml-vs-cargo-lock.html). It seems Cargo also adds things to the `.gitignore` itself, so the boilerplate probably isn't necessary.

It seems like `Cargo.toml` is similar to a header file, where it specifies dependencies, and `Cargo.lock` is more like `package-lock.json` for Node.js projects. The reason we don't want `Cargo.lock` for libraries is that users of the library won't be interested in the particular versions of dependencies used to build it - in fact, a program that uses a library will likely have different versions of those same dependencies itself, so the versions would likely conflict. Libraries have something called `SemVer` which dictates compatibility.

See [here](https://doc.rust-lang.org/cargo/reference/manifest.html) for a detailed look at `Cargo.toml` fields for specifying package information.

Added a debug configuration to `.vscode/launch.json` and debugging works very well inside VSCode.
