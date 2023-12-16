openstreetmap-tile-server with pre-imported poland tiles. In contrary to the base image, this one have all maps precompiled, so there is no need to

Prerequisities:

Docker or Docker Desktop installed
How to run:

In case of a "Got permission denied(...)" error use a "sudo" prefix when running docker commands

run image
docker run \
-p 80:80 \
--shm-size="192m" \
-e "OSM2PGSQL_EXTRA_ARGS=-C 1024" \
-e THREADS=10 \
-d marhev/open_street_maps:01.24 \
run
(defaults are shm-size=64m; OSM2PGSQL_EXTRA_ARGS=-C 800; THREADS=4)

If you know your setup, you can tweak this parameters for smoother tile serving.

shm-size - shared memory limit

OSM2PGSQL_EXTRA_ARGS - RAM cache

THREADS - self-explanatory

Tags
Tags are a date in format mm.yy that lets us know when tiles were updated.

Image based on: https://github.com/Overv/openstreetmap-tile-server
