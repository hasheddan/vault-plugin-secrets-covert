# Vault Covert Secrets Plugin

**NOTICE:** This repo is being donated to HashiCorp. It will continue to be maintained there.

---

Covert is an exmaple secrets engine plugin for [HashiCorp Vault](https://www.vaultproject.io/). It is meant for demonstration purposes only and should never be used in production.

## Usage

All commands can be run using the provided [Makefile](./Makefile). However, it may be instructive to look at the commands to gain a greater understanding of how Vault registers plugins. Using the Makefile will result in running the Vault server in `dev` mode. Do not run Vault in `dev` mode in production.

This will build the plugin binary and start the Vault dev server:
```
# Build Covert plugin and start Vault dev server with plugin automatically registered
$ make
```

Now open a new terminal window and run the following commands:
```
# Open a new terminal window and export Vault dev server http address
$ export VAULT_ADDR='http://127.0.0.1:8200'

# Enable the Covert plugin
$ make enable

# Write a secret to the Covert secrets engine
$ vault write covert/test hello="world"
Success! Data written to: covert/test

# Retrieve secret from Covert secrets engine
$ vault read covert/test
Key      Value
---      -----
hello    world
```

## License

[LICENSE](./LICENSE)
