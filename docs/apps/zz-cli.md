# zz-cli

A CLI app for ZryteZene written in Rust.

## Usage
```shell
$ zz-cli -h
Usage: zz-cli <COMMAND>

Commands:
  login  Login to the ZryteZene APIs.
  music  Music commands.
  tui    Terminal UI for ZryteZene.
  help   Print this message or the help of the given subcommand(s)

Options:
  -h, --help  Print help
```

## Compiling

1. `$ git clone https://git.theclashfruit.me/ThatCakeID/zz-cli.git`.
2. `$ cd zz-cli`.
3. `$ cargo build` or `$ cargo build --release` for a smaller size.

## Contributing

#### Where is everything located?:

* `src/commands`: All available commands for the user.
* `src/tui`: The Terminal UI version (`zz-cli tui`).
* `src/utils`: Frequently used functions in the app.
* `src/structs`: Structs for Serde for the API jsons.

#### Commit message guide:

* `docs: commit_message`: Used when adding something to the docs.
* `feat: commit_message`: Used when adding something to the app.
* `fix: commit_message`: Used when fixing something in the app.

#### Pull Request guide:

* Just describe your changes in an understandable way.

## Links

* [Git Repo](https://git.theclashfruit.me/ThatCakeID/zz-cli)
* [Releases](https://git.theclashfruit.me/ThatCakeID/zz-cli/releases)
* [License](https://git.theclashfruit.me/ThatCakeID/zz-cli/src/branch/main/LICENSE)