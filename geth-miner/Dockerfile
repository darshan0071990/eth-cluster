FROM ffaerber/go-ethereum:latest

# create local directory
RUN mkdir /privatechain

# add files for ethereum chain
ADD genesis.json /privatechain/genesis.json
ADD passfile /privatechain/passfile

# init ethereum chain andd create first account
RUN geth --datadir "/privatechain" init /privatechain/genesis.json
RUN geth --datadir "/privatechain" --password /privatechain/passfile account new | awk -F '[{}]' '{print $(NF-1)}' > /privatechain/accID
RUN mkdir /privatechain/.ethash

# define entry point
ENTRYPOINT ["geth"]
