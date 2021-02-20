A simple `Dockerfile` is available in this repo if you'd like to build it yourself. The official build is also available from dockerhub here: https://hub.docker.com/r/meisnate12/plex-meta-manager

```shell
docker run -it -v <PATH_TO_CONFIG>:/config:rw meisnate12/plex-meta-manager
```
* The `-it` allows you to interact with the script when needed. 
  * For example, it's required in order to go through the OAuth flow while connecting to Trakt or MyAnimeList.
* The `-v <PATH_TO_CONFIG>:/config:rw` mounts the location you choose as a persistent volume to store your files. 
  * Change `<PATH_TO_CONFIG>` to a folder where your config.yml and other files are. 
  * The docker image defaults to running the config named `config.yml` in your persistent volume.
  * Use quotes around the whole thing if your path has spaces i.e. `-v "<PATH_TO_CONFIG>:/config:rw"`

Example

```shell
docker run -it -v "X:\Media\Plex Meta Manager\config:/config:rw" meisnate12/plex-meta-manager
```


### Shell Commands

| Name | Command | Allowed Values | Default Value |
| :-- | :-- | :-- | :-- |
| [Config](#config) | `-c` or `--config` | Path to YAML config file | `config/config.yml` alongside<br>`plex_meta_manager.py` |
| [Time to Run](#time-to-run) | `-t` or `--time` | Time to update each day<br>**Format:** HH:MM | `03:00` |
| [Run](#run) | `-r` or `--run` | Run without the scheduler | `False` |
| [Run Tests](#run-tests) | `-rt`, `--tests`, or `--run-tests` | Run in debug mode with only collections that have `test: true` | `False` |
| [Run Collections](#run-collections) | `-cl` or `--collections` | Process only specified collections (comma-separated list) | ` ` |
| [Divider Character](#divider-character--screen-width) | `-d` or `--divider` | Character that divides the sections | `=` |
| [Screen Width](#divider-character--screen-width) | `-w` or `--width` | Integer between 90 and 300 | `100` |

## Config
To choose the location of the YAML config file

```shell
docker run -it -v "X:\Media\Plex Meta Manager\config:/config:rw" meisnate12/plex-meta-manager --config <path_to_config>
```

## Time to Run
To choose the time when the script will run each day

```shell
docker run -it -v "X:\Media\Plex Meta Manager\config:/config:rw" meisnate12/plex-meta-manager --config /configs/config.yml --time 22:00
```

## Run
To just run the script without having it continuously run use the --run option

```shell
docker run -it -v "X:\Media\Plex Meta Manager\config:/config:rw" meisnate12/plex-meta-manager --config /configs/config.yml --run
```

## Run Tests
To run the script in debug mode while only running collections that have `test: true` use the --run-tests option

```shell
docker run -it -v "X:\Media\Plex Meta Manager\config:/config:rw" meisnate12/plex-meta-manager --config /configs/config.yml --run-tests
```

## Run Collections
To have the script run only using the collections in the comma-separated list use the --collections option

```shell
docker run -it -v "X:\Media\Plex Meta Manager\config:/config:rw" meisnate12/plex-meta-manager --config /configs/config.yml --collections "Harry Potter, Star Wars"
```

## Divider Character & Screen Width
To change the terminal output divider character or width use --divider and --width

```shell
docker run -it -v "X:\Media\Plex Meta Manager\config:/config:rw" meisnate12/plex-meta-manager --divider * --width 200
```
