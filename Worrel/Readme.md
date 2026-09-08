git clone https://github.com/worrellchain/worrell.git
cd worrell
git checkout vp.1.2
make install

mkdir -p $HOME/.worrell/cosmovisor/genesis/bin
cp $HOME/go/bin/worrelldd $HOME/.worrell/cosmovisor/genesis/bin/

sudo ln -s $HOME/.worrell/cosmovisor/genesis $HOME/.worrell/cosmovisor/current -f
sudo ln -s $HOME/.worrell/cosmovisor/current/bin/kiichaind /usr/local/bin/kiichaind -f


worrelld init Vinjan.Inc --chain-id worrell-testnet-1

wget https://raw.githubusercontent.com/worrellchain/networks/refs/heads/main/worrell-testnet-1/genesis.json


# ~/.worrell/config/config.toml  -> [p2p]
persistent_peers = "bb9164c1bd9ed9ff2c0fd9e09b23285698e231de@164.68.98.186:26656"

# ~/.worrell/config/app.toml
minimum-gas-prices = "0.025uworrell"

