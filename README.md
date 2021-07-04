# Fixing linux microphone noise
Fixing my microphone in linux

## Solving
To solve the noise of the mic, you can just run this (ALERT: This will set the microphone volume to 100%)
```bash
$ pactl load-module module-echo-cancel aec_method=webrtc sink_properties=device.description="Noise_Reduction" aec_args="analog_gain_control=0\ digital_gain_control=0"
```

To always start the computer with that configuration you can do the following:
```bash
## Open the pulse config file with a text editor (one of the following):
$ sudo vim /etc/pulse/default.pa
$ sudo gedit /etc/pulse/default.pa
$ sudo xed /etc/pulse/default.pa
$ sudo subl /etc/pulse/default.pa

## Add this line at the end of the file, save and restart the computer
load-module module-echo-cancel aec_method=webrtc sink_properties=device.description="Noise_Reduction" aec_args="analog_gain_control=0\ digital_gain_control=0"
```

## Reference
[Youtube video](https://www.youtube.com/watch?v=9eISgVV5T7M)

# Leonardo Zanotti