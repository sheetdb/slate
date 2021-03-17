# Official [SheetDB](https://sheetdb.io) documentation

Welcome to the official documentation for SheetDB.io, the REST API for Google Spreadsheets.

This repository contains our documentation available at [https://docs.sheetdb.io](https://docs.sheetdb.io/).

If you'd like to correct or add something, please [submit a pull request](https://github.com/sheetdb/docs/pulls). See below for instructions on how to run this page locally, we are using [Slate](https://github.com/slatedocs/slate) to power our documentation.

### Prerequisites

You're going to need:

 - **Linux or macOS** — Windows may work, but is unsupported.
 - **Ruby, version 2.3.1 or newer**
 - **Bundler** — If Ruby is already installed, but the `bundle` command doesn't work, just run `gem install bundler` in a terminal.

### Getting Set Up

1. Fork this repository on GitHub.
2. Clone *your forked repository* (not our original one) to your hard drive with `git clone https://github.com/YOURUSERNAME/slate.git`
3. `cd docs`
4. Initialize and start Slate. You can either do this locally, or with Vagrant:

```shell
# either run this to run locally
bundle install
bundle exec middleman server

# OR run this to run with vagrant
vagrant up
```

You can now see the docs at http://localhost:4567. Whoa! That was fast!

Now that Slate is all set up on your machine, you'll probably want to learn more about [editing Slate markdown](https://github.com/slatedocs/slate/wiki/Markdown-Syntax), or [how to publish your docs](https://github.com/slatedocs/slate/wiki/Deploying-Slate).

If you'd prefer to use Docker, instructions are available [in the wiki](https://github.com/slatedocs/slate/wiki/Docker).

### Production build

To build a production version of all files, run this command:

```shell
bundle exec middleman build --clean
```

### Note on JavaScript Runtime

For those who don't have JavaScript runtime or are experiencing JavaScript runtime issues with ExecJS, it is recommended to add the [rubyracer gem](https://github.com/cowboyd/therubyracer) to your gemfile and run `bundle` again.

### Stay in touch

- Email - [support@sheetdb.io](mailto:support@sheetdb.io)
- Website - [https://sheetdb.io](https://sheetdb.io/)
- Twitter - [@sheetdb_io](https://twitter.com/sheetdb_io)