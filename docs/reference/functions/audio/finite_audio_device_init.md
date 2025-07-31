# finite_audio_device_init

```c
bool finite_audio_device_init()
```

The `finite_audio_device_init`attempts to create a new [`FinitePlaybackDevice`](../../../types/FinitePlaybackDevice)

## Code Example

```c
    #include <finite/audio.h>
    #include <finite/log.h>

    FinitePlaybackDevice *dev = finite_audio_device_init();
    char *jingle = "jingle2.mp3";

    finite_audio_get_audio_params(jingle, dev);
    // print out the audio duration
    finite_audio_get_audio_duration(dev);

    // use params to init audio
    finite_audio_init_audio(dev, jingle, false);

    // audio is made so now play

    finite_audio_play(dev);
    FINITE_LOG("Done\n");
    // clean up when finished
    finite_audio_cleanup(dev);
```


## Notes

As of v0.6.0 [`FinitePlaybackDevice`](../../../types/FinitePlaybackDevice) is not attached to a window. That is subject to change.

## Standard Usage

This function should be created once for a single audio. Do not reuse [`FinitePlaybackDevices`](../../../types/FinitePlaybackDevice).

## Related Docs

[`FinitePlaybackDevice`](../../../types/FinitePlaybackDevice)
