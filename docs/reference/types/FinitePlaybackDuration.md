# FinitePlaybackDuration 

<div class="alert alert-info part text-info">
❔ FinitePlaybackDuration  was last modified in <b>0.4.9</b>
</div>

```c
typedef struct FinitePlaybackDuration FinitePlaybackDuration;
struct FinitePlaybackDuration {
    double trueSeconds;
    int hours;
    int minutes;
    int seconds;
    int milliseconds;
};
```

The `FinitePlaybackDuration` struct refers to a single audio's duration.

## Properties

| Type                          | Decription                                                                                                                            |
| ----------------------------- | ------------------------------------------------------------------------------------------------------------------------------------- |
|`double trueSeconds`|The true duration of the audio in seconds|
|`int hours`| The amount of hours in the audio's duration.|
|`int minutes`| The minutes in the audio's duration (after calculating the hours) |
|`int seconds`| The seconds in the audio's duration (after calculating the minutes) |
|`int milliseconds`| The ms in the audio's duration (after calculating the seconds) |

## Standard Usage

This struct should be created with [`finite_audio_get_audio_duration`](../../functions/audio/finite_audio_get_audio_duration) and destroyed with [`finite_audio_cleanup`](../../functions/audio/finite_audio_cleanup)

## Related Docs

[`finite_audio_get_audio_duration`](../../functions/audio/finite_audio_get_audio_duration)<br>
[`finite_audio_cleanup`](../../functions/audio/finite_audio_cleanup)
