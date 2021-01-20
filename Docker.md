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
docker run -it -v "X:\Media\Plex Meta Manager:/config:rw" meisnate12/plex-meta-manager
```


### Shell Commands

| Name | Command | Allowed Values | Default Value |
| :-- | :-- | :-- | :-- |
| [Config](#config) | `-c` or `--config` | Path to YAML config file | `config/config.yml` alongside<br>`plex_meta_manager.py` |
| [Time to Run](#time-to-run) | `-t` or `--time` | Time to update each day<br>**Format:** HH:MM | `03:00` |
| [Run](#run) | `-r` or `--run` | Run without the scheduler | `False` |
| [Divider Character](#divider-character--screen-width) | `-d` or `--divider` | Character that divides the sections | `=` |
| [Screen Width](#divider-character--screen-width) | `-w` or `--width` | Integer between 90 and 300 | `100` |

## Config
To choose the location of the YAML config file

```shell
docker run -it -v "X:\Media\Plex Meta Manager:/config:rw" meisnate12/plex-meta-manager --config-path <path_to_config>
```

## Time to Run
To choose the time when the script will run each day

```shell
docker run -it -v "X:\Media\Plex Meta Manager:/config:rw" meisnate12/plex-meta-manager --config-path /configs/config.yml --time 22:00
```

## Run
To just run the script without having it continuously run use the --run option

```shell
docker run -it -v "X:\Media\Plex Meta Manager:/config:rw" meisnate12/plex-meta-manager --config-path /configs/config.yml --run
```
## Divider Character & Screen Width
To change the terminal output divider character or width use --divider and --width

```shell
docker run -it -v "X:\Media\Plex Meta Manager:/config:rw" meisnate12/plex-meta-manager --divider * --width 200
```
