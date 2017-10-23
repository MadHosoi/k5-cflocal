# k5-cflocal demo

If docker don not starts automatically
docker-machine start default

local.yml => In order to configurate local instance of the droplet.

cf local stage k5-cflocal-sample

# Errors

time="2017-10-23T12:17:52+02:00" level=info msg="Unable to use system certificate pool: crypto/x509: system root pool is not available on Windows"

Error: error during connect: Post https://192.168.99.100:2376/build?buildargs=null&cachefrom=null&cgroupparent=&cpuperiod=0&cpuquota=0&cpusetcpus=&cpusetmems=&cpushares=0&dockerfile=&forcerm=1&labels=null&memory=0&memswap=0&networkmode=&pull=1&rm=1&shmsize=0&t=cflocal&ulimits=null: dial tcp 192.168.99.100:2376: connectex: A connection attempt failed because the connected party did not properly respond after a period of time, or established connection failed because connected host has failed to respond.
