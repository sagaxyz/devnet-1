# README

## Generate your gentx
```
scpd add key <validator_key_name>
```
Make sure you are saving the generated `mnemonic` and `~/.spc/config/node_key.json`. You can alternatively use an existing mnemonic (--recover). This has to match the address already provided to SAGA.

```
spcd init --chain-id=spc-devnet-1 --recover --default-denom upsaga <your_moniker>
cp <provided_genesis_file> ~/.spc/config/genesis.json
spcd gentx <validator_key_name> "1500000stake" --chain-id spc-devnet-1 --ip spc.<your_validator_moniker>.spc-devnet-1.<route53_zone>
```

The public address has to be from a subdomain you control on Route53.

## Submit your gentx
After copying your gentx file under the folder `./gentx` submit a PR on this repo and we will use it to generate the signed genesis.
