# finite_audio_pause

<div class="alert alert-info part text-info">
❔  finite_audio_pause was last modified in <b>v0.6.0</b>.
</div>

```c
bool finite_audio_pause(FinitePlaybackDevice *dev)
```

The ` finite_audio_pause` attempts to pause or unpause an audio file from a [`FinitePlaybackDevice`](../../../types/FinitePlaybackDevice).

# Parameters

| Type                        | Decription                                                                                        |
| --------------------------- | ------------------------------------------------------------------------------------------------- |
| `FinitePlaybackDevice *dev` | The [`FinitePlaybackDevice`](../../../types/FinitePlaybackDevice) to get the audio to pause from. |

## Notes

This function only works in a multi-threaded environment. Calling this function in the same thread as [`finite_audio_play`](../finite_audio_play) makes this function a NOP.

This function can both pause and unpause functions, while the now depricated [`finite_audio_unpause`](../finite_audio_unpause) function can only unpause paused audio. Use this function instead.

## Standard Usage

This function requires a valid [`FinitePlaybackDevice`](../../../types/FinitePlaybackDevice).

## Related Docs

[`finite_audio_play`](../finite_audio_play)<br>
[`finite_audio_unpause`](../finite_audio_unpause)<br>
[`FinitePlaybackDevice`](../../../types/FinitePlaybackDevice)
