# finite_audio_cleanup

<div class="alert alert-info part text-info">
❔  finite_audio_cleanup was last modified in <b>v0.6.0</b>.
</div>

```c
void finite_audio_cleanup(FinitePlaybackDevice *dev)
```

The ` finite_audio_pause` attempts to pause or unpause an audio file from a [`FinitePlaybackDevice`](../../../types/FinitePlaybackDevice).

# Parameters

| Type                        | Decription                                                                                        |
| --------------------------- | ------------------------------------------------------------------------------------------------- |
| `FinitePlaybackDevice *dev` | The [`FinitePlaybackDevice`](../../../types/FinitePlaybackDevice) to destroy. |

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


## Standard Usage

This function requires a valid [`FinitePlaybackDevice`](../../../types/FinitePlaybackDevice).

## Related Docs

[`finite_audio_play`](../finite_audio_play)<br>
[`FinitePlaybackDevice`](../../../types/FinitePlaybackDevice)
