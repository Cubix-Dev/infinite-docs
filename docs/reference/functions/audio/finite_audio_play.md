# finite_audio_play

<div class="alert alert-info part text-info">
❔  finite_audio_play was last modified in <b>v0.6.0</b>.
</div>

```c
void finite_audio_play(FinitePlaybackDevice *dev)
```

The ` finite_audio_play` attempts to play an audio file from a [`FinitePlaybackDevice`](../../../types/FinitePlaybackDevice)

# Parameters

| Type                        | Decription                                                                                        |
| --------------------------- | ------------------------------------------------------------------------------------------------- |
| `FinitePlaybackDevice *dev` | The [`FinitePlaybackDevice`](../../../types/FinitePlaybackDevice) to get the audio to play from. |

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

Playing audio is a halting function. For the best performance, handle audio in a seperate thread.

## Related Docs

[`finite_audio_get_audio_params`](../finite_audio_get_audio_params)<br>
[`FinitePlaybackDevice`](../../../types/FinitePlaybackDevice)
