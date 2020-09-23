# README

The PostgreSQL object-relational database system provides reliability and data integrity

⚠️ This project is no longer maintained. ⚠️

## Installation

```sh
# Define installation folder

export INSTALL_DIRECTORY=/usr/bin

# Use local installation

sudo bin/installer install

# Use remote installation

curl --location "https://gitlab.com/timonier/postgresql/raw/master/bin/installer" | sudo sh -s -- install
```

__Note 1__: If you do not define `INSTALL_DIRECTORY`, `installer` will use in `/usr/local/bin`.

__Note 2__: `docker-for-mac` users have to configure [native NFS server](https://medium.com/@sean.handley/how-to-set-up-docker-for-mac-with-native-nfs-145151458adc).

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

## Links

* [image "timonier/postgresql"](https://hub.docker.com/r/timonier/postgresql/)
* [postgresql](https://www.postgresql.org)
* [set up docker for mac with native nfs](https://medium.com/@sean.handley/how-to-set-up-docker-for-mac-with-native-nfs-145151458adc)
