# take geth image with alltools (bootstrap tool)
FROM ffaerber/go-ethereum:latest

# create local data directory for geth
RUN mkdir /privatechain

# copy own bootkey
ADD bootnode.key /privatechain/bootnode.key

# define entrypoint
ENTRYPOINT ["bootnode"]
