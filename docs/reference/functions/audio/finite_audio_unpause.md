# finite_audio_unpause

<div class="alert alert-info part text-info">
❔  finite_audio_unpause was last modified in <b>v0.6.0</b>.
</div>

<div class="alert alert-warning part text-warning">
❔  finite_audio_unpause is depricated as of <b>v0.6.0</b> and may be removed in future. Check the Notes section for more information.
</div>

```c
bool finite_audio_unpause(FinitePlaybackDevice *dev)
```

The ` finite_audio_unpause` attempts to unpause an audio file from a [`FinitePlaybackDevice`](../../../types/FinitePlaybackDevice).

# Parameters

| Type                        | Decription                                                                                        |
| --------------------------- | ------------------------------------------------------------------------------------------------- |
| `FinitePlaybackDevice *dev` | The [`FinitePlaybackDevice`](../../../types/FinitePlaybackDevice) to get the audio to unpause from. |

## Notes

This function only works in a multi-threaded environment. Calling this function in the same thread as [`finite_audio_play`](../finite_audio_play) makes this function a NOP.

This function can only unpause audio, while the newer [`finite_audio_pause`](../finite_audio_pause) function can both pause and unpause audio. Use this [`finite_audio_pause`](../finite_audio_pause) instead.

## Standard Usage

This function requires a valid [`FinitePlaybackDevice`](../../../types/FinitePlaybackDevice).

## Related Docs

[`finite_audio_play`](../finite_audio_play)<br>
[`finite_audio_pause`](../finite_audio_pause)<br>
[`FinitePlaybackDevice`](../../../types/FinitePlaybackDevice)
