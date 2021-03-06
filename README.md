# Sample Readme

## About Searchex Repos and Collections

With Searchex you can publish document repositories on GitHub.  Download and
install a Searchex repository on your host with one simple command.

Each Searchex `repo` contains one or more `collections`.  Each `collection` has
a `config` file - a yaml file with indexing and search parameters.

To install this Sample Repo on your system, use the command:

    searchex fetch elixir-search/sample

Then view your new collections with the command:

    searchex ls
    searchex info

Now you can search any of the collections in the Sample Repo.

## Behind the Scenes

Searchex auto-creates a hidden directory `~/.searchex` on your Searchex host.
Under this directory, there is one subdirectory for each Repo.  Each Repo
directory can contain one or more `config` files.

    ~/.searchex
      |-- local
        |-- collection1.yml
        |-- collection2.yml
      |-- sample
        |-- genesis.yml
        |-- constitution.yml
        |-- dickens.yml
      |-- another_repo
        |-- some_other_config.yml

Things to note:

- Searchex auto-creates a `~/.searchex/local` directory which contains your
  locally-created `config` files. This is your `local` repo.

- You can fetch any other Searchex Repos from GitHub.

- You can add/remove/edit/update any file under `~/.searchex`.  Any sort of Git
  operation (commit/pull/revert/etc) is ok.  

- You can download repos to the `~/.searchex` directory using any method:
  `scp`, `git clone` or `searchex fetch`.

- Document and cache-file locations are defined in the `config` file.  They
  can be located in the repo directory itself, or elsewhere on your filesystem.

Best practices:

- Before publishing a Searchex Repo, test it locally to make sure everything works.

- Package source documents and a cache file in your Repo, so everything is
  self-contained and pre-warmed.
