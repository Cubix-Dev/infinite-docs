# FinitePlaybackDevice

<div class="alert alert-info part text-info">
❔ FinitePlaybackDevice was last modified in <b>0.4.9</b>
</div>

```c
typedef struct FinitePlaybackDevice FinitePlaybackDevice;
struct FinitePlaybackDevice {
    char *name;
    char *filename;
    bool isPlaying;
    bool isPaused;
    short *audioBuffer;
    FinitePlaybackDuration dur;
    snd_pcm_t *device;
    snd_pcm_format_t format;
    snd_pcm_hw_params_t *params;
    snd_pcm_uframes_t frames;
    SNDFILE *file;
    sf_count_t sfFrames;
    uint32_t sample_rate;
    uint32_t channels;
    uint32_t buff_time;
    uint32_t buff_per;
    double freq;
    int verbose;
    int resample;
    int per_event;
};
```

The `FinitePlaybackDevice` struct refers to a single audio player.

## Properties

| Type                          | Decription                                                                                                                            |
| ----------------------------- | ------------------------------------------------------------------------------------------------------------------------------------- |
| `char *name`                  | The name of the audio device in use. Defaults to "default".                                                                           |
| `char *filename`              | The name of the audio in use.                                                                                                         |
| `bool isPlaying`              | Whether the audio stream is being read (the audio is playing sound)                                                                   |
| `bool isPaused`               | Whether the audio is paused.                                                                                                          |
| `short *audioBuffer`          | The [audio period](https://www.alsa-project.org/alsa-doc/alsa-lib/group___p_c_m.html#gab01fcfe9b97382a8d3f2027c664b8b8a).             |
| `FinitePlaybackDuration dur`  | The [`FinitePlaybackDuration`](../FinitePlaybackDuration)                                                                             |
| `snd_pcm_t *device`           | The ALSA device.                                                                                                                      |
| `snd_pcm_format_t format`     | The ALSA format of the audio.                                                                                                         |
| `snd_pcm_hw_params_t *params` | The ALSA audio hardware params.                                                                                                       |
| `snd_pcm_uframes_t frames`    | The size of the [audio period](https://www.alsa-project.org/alsa-doc/alsa-lib/group___p_c_m.html#gab01fcfe9b97382a8d3f2027c664b8b8a). |
| `SNDFILE *file`               | The SND file descriptor for the audio.                                                                                                |
| `sf_count_t sfFrames`         | SND Audio Frames. Used to calcuate the actual audio duration.                                                                         |
| `uint32_t sample_rate`        | The Sample Rate of the audio                                                                                                          |
| `uint32_t channels`           | The number of channels the audio supports. 1 = Mono and 2 = Stereo                                                                    |
| `uint32_t buff_time`          | Unused.                                                                                                                               |
| `uint32_t buff_per`           | Unused.                                                                                                                               |
| `double freq`                 | Unused.                                                                                                                               |
| `int verbose`                 | Unused.                                                                                                                               |
| `int resample`                | The resample rate of the audio.                                                                                                       |
| `int per_event`               | Unused.                                                                                                                               |

## Standard Usage

This struct refers to a single audio. Do not reuse a `FinitePlaybackDevice` for multiple audios.

This struct should be created with [`finite_audio_device_init`](../../functions/audio/finite_audio_device_init) and destroyed with [`finite_audio_cleanup`](../../functions/audio/finite_audio_cleanup)

## Related Docs

[`finite_audio_device_init`](../../functions/audio/finite_audio_device_init)<br>
[`finite_audio_cleanup`](../../functions/audio/finite_audio_cleanup)
