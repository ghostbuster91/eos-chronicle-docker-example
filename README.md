# Example setup of eos chronicle using docker compose


### Preparation
Replace `exp-ws-host = 172.17.0.1` in config.ini with ip of your receiver. 

If receiver will be run on host use `host.docker.internal` for mac, or `ifconfig docker0` for linux.

1. `cd receiver; perl chronicle-ws-dumpler.pl --bin`
2. `docker-compose up -d`
