# Warming up - exercise 1

I picked Rust as the language for this exercise. I have never used Rust, so I will look for the answers from the Internet.

## Linting, testing and building

Linting refers to the use of a static code analysis tool that flags programming and stylistic errors and other suspicious code constructs (see [Wikipedia](<https://en.wikipedia.org/wiki/Lint_(software)>)). As Rust is a language that is compiled to executable code unsing a compiler, the compiler does much of the static code analysis and a separate linter is not needed as much as in interpreted or just-in-time compiled scripting languages. It also seems that the Rust's compilation process [includes](https://rustc-dev-guide.rust-lang.org/diagnostics.html#lints-versus-fixed-diagnostics) use of "[lints](https://rustc-dev-guide.rust-lang.org/diagnostics.html#lints)". However there are some tools that are commonly used for cleaning Rust code stylistically or otherwise improve it. Rustfmt can, for example, be used for formatting Rust code according to style guidelines and Clippy for general linting.

Many central development tasks, such as testing and building, have been integrated into Rust's package manager called Cargo. Cargo allows packages to declare their dependencies and manages obtaining correct versions of them automatically. It normalizes the commands needed to build the package and run its tests. Instead of calling the Rust compiler directly, a package can be built with a generic command `cargo build`, which constructs the correct compiler invocation automatically and fetches any dependencies the package has, arranging for them to be incorporated into the build. Tests are written as Rust functions annotated as tests with `#[test]` line before function definition. Invoking the command `cargo test` builds a test runner that will run the annotated functions.

## Alternatives for Jenkins and GitHub Actions?

There are many ways to set up the CI besides Jenkins and GitHub Actions. For example AlternativeTo.net lists numerous alternative CI/CD solutions. These include for example Travis CI, Gitlab CI, Buildbot, CircleCI and AppVeyor. Rusts Cargo Book gives examples of configuring CI on Travis CI and Gitlab CI in addition to GitHub Actions.

## Self-hosted or cloud-based?

Based on the number of developers (6), the project would seem quite small, which would suggest the use of a cloud based solution. This would make the CI configuration process much easier as the servers themselves don't need to be configured. It is, however, unknown if there is an organization behind the team that could provide it's own self-hosted CI for the team. If there is, it would probably make sense to use that instead.
