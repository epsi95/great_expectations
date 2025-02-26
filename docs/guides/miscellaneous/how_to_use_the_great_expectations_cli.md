---
title: How to use the Great Expectations command line interface (CLI)
---

The Great Expectations command line is organized using a **`<NOUN> <VERB>`** syntax.
This guide is organized by nouns (datasource, suite, docs) then verbs (new, list, edit, etc).

## Basics

You can get a list of Great Expectations commands available to you by typing `great_expectations --v3-api --help`.
Each noun command and each verb sub-command has a description, and should help you find the thing you need.

Please note that the V3 (Batch Request) API can be accessed by adding the `--v3-api` flag after `great_expectations`. Please see our how-to guides and use the `--help` flag for more complete descriptions of the new functionality.

:::info [OPTIONAL_TEXT_HERE]
All Great Expectations commands have help text which you can access by adding `--help` to the end of a command. For example, by running `great_expectations --v3-api suite new --help` you'll see help output for that specific command.
:::

By running `great_expectations --v3-api --help`, you will see all top-level commands that are available in the CLI:

```bash
$ great_expectations --v3-api --help
Usage: great_expectations [OPTIONS] COMMAND [ARGS]...

  Welcome to the great_expectations CLI!

  Most commands follow this format: great_expectations <NOUN> <VERB>

  The nouns are: checkpoint, datasource, docs, init, project, store, suite,
  validation-operator. Most nouns accept the following verbs: new, list,
  edit

Options:
  --version                Show the version and exit.
  --v2-api / --v3-api      Default to v2 (Batch Kwargs) API. Use --v3-api for
                           v3 (Batch Request) API

  -v, --verbose            Set great_expectations to use verbose output.
  -c, --config TEXT        Path to great_expectations configuration file
                           location (great_expectations.yml). Inferred if not
                           provided.

  -y, --assume-yes, --yes  Assume "yes" for all prompts.
  --help                   Show this message and exit.

Commands:
  checkpoint  Checkpoint operations
  datasource  Datasource operations
  docs        Data Docs operations
  init        Initialize a new Great Expectations project.
  project     Project operations
  store       Store operations
  suite       Expectation Suite operations
```

You can further explore available options and commands with the `--help` flag, for example:

```bash
$ great_expectations --v3-api datasource --help
Using v3 (Batch Request) API
Usage: great_expectations datasource [OPTIONS] COMMAND [ARGS]...

  Datasource operations

Options:
  --help  Show this message and exit.

Commands:
  delete  Delete the datasource specified as an argument
  list    List known Datasources.
  new     Add a new Datasource to the data context.
```

## Shell autocompletion for the CLI

If you want to enable autocompletion for the Great Expectations CLI, you can execute following commands in your shell (or add them to your .bashrc/.zshrc or ~/.config/fish/completions/):

```bash title="bash"
$ eval "$(_GREAT_EXPECTATIONS_COMPLETE=source_bash great_expectations)"
```

```zsh title="zsh"
$ eval "$(_GREAT_EXPECTATIONS_COMPLETE=source_zsh great_expectations)"
```

```fish title="fish"
$ eval (env _GREAT_EXPECTATIONS_COMPLETE=source_fish great_expectations)
```

(you'll have to create a ~/.config/fish/completions/great_expectations.fish file).

Alternatively, if you don't want the eval command to slow down your shell startup time, you can instead add the commands as a script to your shell profile. For more info, see the official [Click documentation](https://click.palletsprojects.com/en/7.x/bashcomplete/)

