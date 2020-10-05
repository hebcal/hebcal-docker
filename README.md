# hebcal-docker
`Dockerfile`s to build images that run `hebcal`.

Just `docker build` and you'll get a `hebcal` image that will work anywhere you can run Docker.

`ubuntu` results in a ~75M image:

    docker build -t hebcal - < Dockerfile.ubuntu
    docker run hebcal ...

`alpine` results in a ~7M image:

    docker build -t hebcal - < Dockerfile.alpine
    docker run hebcal ...

To build for a default city other than `New York`, just add a
`--build-arg="$CITY"` flag. For details on cities at both build-time and
runtime, see:

- https://github.com/hebcal/hebcal#build--install
- https://github.com/hebcal/hebcal#candle-lighting-times

Alternatively change city at runtime:
`docker run -e HEBCAL_CITY="${CITY}" --rm hebcal...`
`docker run --rm hebcal -C ${CITY} ...`
