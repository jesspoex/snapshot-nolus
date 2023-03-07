# snapshot-nolus

# stop the service and reset the data
```
sudo apt update && sudo apt upgrade
```
## download latest snapshot
```
curl -L https://nolus.jesspoex.site/snapshot/nolus/nolus-snapshot-20230306.tar.lz4| tar -Ilz4 -xf - -C $HOME/.nolus
mv $HOME/.nolus/priv_validator_state.json.backup $HOME/.nolus/data/priv_validator_state.json
```
## restart the service and check the log
```
sudo systemcl start nolusd && sudo journalctl -u nolusd -f --no-hostname -o cat
```
