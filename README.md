# prepare_release.{sh,nu}

I use this for a couple of projects to keep my Cargo version in sync with git
and automate the process of releasing new versions locally.

Available for both Bash and Nushell.

Both scripts do the following:

- Check current Cargo.toml version
- Ask for the new version you want to release
- Update Cargo.toml and Cargo.lock (via `cargo check`)
- Commit and tag the new version
- Push the new version and updated Cargo.{lock,toml} to GitHub
- Commit is titled "chore: release v(new version)"

In my case, the tag is used as a trigger and kicks off a GitHub Actions workflow
that checks, builds, and publishes the latest version of my
[portfolio](https://github.com/jamesukiyo/jamesukiyo.github.io).

I don't publish anything to crates.io but I hope it's useful for someone that
does - if your workflow is similar.

## Usage:

Bash version:

```bash
./prepare_release.sh
or
bash ./prepare_release.sh
```

Nushell version:

```nu
prepare_release.nu
# or
nu ./prepare_release.nu
```

## Contributing

Pull requests and issues are welcome. If you believe the script can be improved
or is missing a feature, I'm happy to add it if it doesn't break the existing
functionality.

## License

Copyright (c) 2025-now PlumJam <git@plumj.am>

This project is licensed under the MIT license ([LICENSE] or
<http://opensource.org/licenses/MIT>)

[LICENSE]: ./LICENSE
