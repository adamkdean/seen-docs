# server setup

    1 x 512 Droplet Ubuntu 14.04.4 x64
    seen.akd.io ~ 188.166.153.80

## Initial server setup

    $ curl -sSL https://get.docker.com/ | sh
    $ git clone git@github.com:seenproject/api


    $ git clone git@github.com:seenproject/website

## Docker setup to default bind to eth1 instead of eth0

    $ nano /etc/default/docker

    ETH1_IP=$(ifconfig eth1 | grep "inet addr" | awk -F: '{print $2}' | awk '{print $1}')
    DOCKER_OPTS="-H unix://var/run/docker.sock --ip=$ETH1_IP"

## Mongo setup

    $ git clone git@github.com:seenproject/mongodb
    $ cd mongodb
    $ ./mongodb.sh
    Service doesn't exist, creating...
    Data volume doesn't exists...creating it
    mongodb-data
    Unable to find image 'mongo:3.2' locally
    3.2: Pulling from library/mongo
    8dddc0afbe0a: Pull complete
    a3ed95caeb02: Pull complete
    32eed1053be0: Pull complete
    da7450003e70: Pull complete
    da146c968d58: Pull complete
    8d84cf004260: Pull complete
    255da74532aa: Pull complete
    f181c41a6a52: Pull complete
    2a183ef32b8b: Pull complete
    03913f2c5b05: Pull complete
    Digest: sha256:5d3690ca2cc76131539498a0da4f77c611dd654f3fcacf5b1499a99f3ebc5b2f
    Status: Downloaded newer image for mongo:3.2
    f6730967621ee5756af380b9e7302f08556980a8e766981617215577175cf278
    Service should now be running...
    f6730967621e        mongo:3.2           "/entrypoint.sh --nop"   1 seconds ago       Up Less than a second   *snip*:27017->27017/tcp   mongodb-server

## Worker setup

    $ git clone git@github.com:seenproject/worker
    $ export TMDB_API_KEY=*snip*
    $ export MONGODB_URI=mongodb://*snip*:27017/seen
    $ ./build/docker.sh
    ...
