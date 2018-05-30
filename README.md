## Running local dev environment

### Build dev environment

```bash
./dev.sh build
```

### Init/Reset Tendermint blockchain data

```bash
DOCKER/reset_tendermint.sh
```

### Run dev environment

Before first time run the dev environment, you must init the Tendermint blockchain first (see [Init/Reset Tendermint blockchain data](#init-reset-tendermint-blockchain-data))

First of all, if your source go files locate at `src/` and main file is called `main.go`, then you can simply run:

```bash
./dev.sh up
```

Or else you need to change them in `.env` file first:

```
SOURCE=../src
MAIN_GO=main.go
```

### dev.sh

The `dev.sh` is just a shortcut for `docker-compose`:

```bash
docker-compose -f DOCKER/docker-compose.yml
```

So you can call all `docker-compose` command as you wish.