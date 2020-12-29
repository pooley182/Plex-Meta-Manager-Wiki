A simple `Dockerfile` is available in this repo if you'd like to build it yourself. The official build is also available from dockerhub here: https://hub.docker.com/r/meisnate12/plex-meta-manager

```shell
docker run --rm -v '/mnt/user/plex-meta-manager/':'/config':'rw' 'meisnate12/plex-meta-manager' -u
```

The `-v '/mnt/user/plex-auto-collections/':'/config'` mounts a persistent volume to store your config file. Today, the docker image defaults to running the config named `config.yml` in your persistent volume (eventually, the docker will support an environment variable to change the config path).

Lastly, you may need to run the docker with `-it` and without `-u` in order to interact with the script. For example, if you'd like to use Trakt lists, you need to go through the OAuth flow and interact with the script at first-run. After that, you should be able to run it without the `-it` flag.