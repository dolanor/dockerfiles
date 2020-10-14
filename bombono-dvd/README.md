# Bombono DVD authoring tool

# Run

```
xhost +
docker run --rm -v $PWD:/mnt -v /tmp/.X11-unix:/tmp/.X11-unix -e DISPLAY=unix$DISPLAY dolanor/bombono
```
