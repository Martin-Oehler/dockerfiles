# kalibr Docker file

Build with
```
docker build . -t kalibr-melodic
```

Go to the folder with your calibration bag und run with
```
xhost +local:root # for the lazy and reckless
docker run -it --env="DISPLAY" --env="QT_X11_NO_MITSHM=1" --volume="/tmp/.X11-unix:/tmp/.X11-unix:rw" -v $(pwd):/mnt kalibr-melodic
```

Start calibration with `kalibr_calibrate_cameras ...`

e.g., for Insta360 Pro2:

```
kalibr_calibrate_cameras --bag insta360_pro_2021-06-14-16-07-14.bag --topics /camera360/origin1/image_raw_throttled /camera360/origin2/image_raw_throttled /camera360/origin3/image_raw_throttled /camera360/origin4/image_raw_throttled /camera360/origin5/image_raw_throttled /camera360/origin6/image_raw_throttled --models omni-radtan omni-radtan omni-radtan omni-radtan omni-radtan omni-radtan --target april_6x6_50x50cm.yaml --bag-from-to 400 800

```
