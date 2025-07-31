# finite_audio_stop

<div class="alert alert-info part text-info">
❔  finite_audio_stop was last modified in <b>v0.6.0</b>.
</div>

```c
bool  finite_audio_stop(FinitePlaybackDevice *dev)
```

The ` finite_audio_stop` attempts to stop an audio file from a [`FinitePlaybackDevice`](../../../types/FinitePlaybackDevice)

# Parameters

| Type                        | Decription                                                                                        |
| --------------------------- | ------------------------------------------------------------------------------------------------- |
| `FinitePlaybackDevice *dev` | The [`FinitePlaybackDevice`](../../../types/FinitePlaybackDevice) to get the audio to stop from. |

## Notes

This function only works in a multi-threaded environment. Calling this function in the same thread as [`finite_audio_play`](../finite_audio_play) makes this function a NOP.

## Standard Usage

This function requires a valid [`FinitePlaybackDevice`](../../../types/FinitePlaybackDevice).

## Related Docs

[`finite_audio_play`](../finite_audio_play)<br>
[`FinitePlaybackDevice`](../../../types/FinitePlaybackDevice)
