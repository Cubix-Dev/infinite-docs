# finite_audio_init_audio

<div class="alert alert-info part text-info">
❔  finite_audio_init_audio was last modified in <b>v0.6.0</b>.
</div>

```c
bool  finite_audio_init_audio(FinitePlaybackDevice *dev,  char* audio, bool autoCreate)
```

The ` finite_audio_init_audio` attempts to attach an audio file to a [`FinitePlaybackDevice`](../../../types/FinitePlaybackDevice)

# Parameters

| Type                        | Decription                                                                                                |
| --------------------------- | --------------------------------------------------------------------------------------------------------- |
| `FinitePlaybackDevice *dev` | The [`FinitePlaybackDevice`](../../../types/FinitePlaybackDevice) to attach the audio to.         |
| `char* audio`               | The path to the audio file                                                                                |
| `bool autocreate            | Determines if this function should attempt to grab the hardware params for the audio before attaching it. |

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

The autocreate param determines if the audio params should be grabbed automatically. If you previously called [`finite_audio_get_audio_params`](../finite_audio_get_audio_params) you **MUST** set this to false.

## Standard Usage

This function requires a valid [`FinitePlaybackDevice`](../../../types/FinitePlaybackDevice).

The path to the audio is relative to the package. As such you should bundle your audio into your project with meson.

## Related Docs

[`finite_audio_get_audio_params`](../finite_audio_get_audio_params)<br>
[`FinitePlaybackDevice`](../../../types/FinitePlaybackDevice)
