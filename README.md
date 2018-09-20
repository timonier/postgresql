# README

The PostgreSQL object-relational database system provides reliability and data integrity

## Installation

```sh
# Define installation folder

export INSTALL_DIRECTORY=/usr/bin

# Use local installation

sudo bin/installer install

# Use remote installation

curl --location "https://github.com/timonier/postgresql/raw/master/bin/installer" | sudo sh -s -- install
```

__Note__: If you do not define `INSTALL_DIRECTORY`, `installer` will use in `/usr/local/bin`.

## Usage

### pg_dump

Run the command `pg_dump`:

```sh
# See all pg_dump options

pg_dump --help

# Run pg_dump

export PGHOST=postgresql-morgan.docker
export PGPASSWORD=my-super-password
export PGUSER=postgres

pg_dump api --blobs --data-only --disable-triggers --file backup.sql
```

### psql

Run the command `psql`:

```sh
# See all psql options

psql --help

# Run psql

export PGHOST=postgresql-morgan.docker
export PGPASSWORD=my-super-password
export PGUSER=postgres

psql --file backup.sql api
```

## Contributing

1. Fork it.
2. Create your branch: `git checkout -b my-new-feature`.
3. Commit your changes: `git commit -am 'Add some feature'`.
4. Push to the branch: `git push origin my-new-feature`.
5. Submit a pull request.

__Note__: Use the script `bin/build` to test your modifications locally.

If you like / use this project, please let me known by adding a [★](https://help.github.com/articles/about-stars/) on the [GitHub repository](https://github.com/timonier/postgresql).

## Links

* [image "timonier/postgresql"](https://hub.docker.com/r/timonier/postgresql/)
* [postgresql](https://www.postgresql.org)
* [timonier/dumb-entrypoint](https://github.com/timonier/dumb-entrypoint)
