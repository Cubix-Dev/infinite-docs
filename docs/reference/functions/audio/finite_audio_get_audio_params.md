# finite_audio_get_audio_params

<div class="alert alert-info part text-info">
❔ finite_audio_get_audio_params was last modified in <b>v0.6.0</b>.
</div>

```c
bool finite_audio_get_audio_params(FinitePlaybackDevice *dev, char* audio)
```

The `finite_audio_get_audio_params` gives the required audio hardware params for a given a audio file to a [`FinitePlaybackDevice`](../../../types/FinitePlaybackDevice)

# Parameters

| Type                        | Decription                                                                                        |
| --------------------------- | ------------------------------------------------------------------------------------------------- |
| `FinitePlaybackDevice *dev` | The [`FinitePlaybackDevice`](../../../types/FinitePlaybackDevice) to get the audio params for. |
| `char* audio` | The path to the audio file |

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

This function should only be call **once** per [`FinitePlaybackDevice`](../../../types/FinitePlaybackDevice).

## Standard Usage

This function requires a valid [`FinitePlaybackDevice`](../../../types/FinitePlaybackDevice). 

## Related Docs

[`FinitePlaybackDevice`](../../../types/FinitePlaybackDevice)
