# tts

Dependencies: `jq`, `curl`

Interact with [StreamLabs](https://streamlabs.com/) TTS API endpoint.

## Usage

```
Usage ./tts [-h] [-v VOICE] [-d FILENAME|-p] <text_to_speak>
Converts text to speech using the StreamLabs API
Any other positional arguments are interpreted as the text input
If no text is present, reads from STDIN

   -h           Prints this help message and exits
   -v VOICE     Change the voice used for TTS
   -l           List available voices
   -d FILENAME  Download the .ogg file to FILENAME.ogg [default]
   -p           Instead of downloading, print the audio URL
```

## Install

* Install [`curl`](https://github.com/curl/curl) and [`jq`](https://stedolan.github.io/jq/download/)
* Downlaod the `tts` script somewhere on your `$PATH`:
  * `curl <TODO> -o ~/.local/bin/tts`
  * or use `sinister`: TODO

## Examples

```
tts -l  # to list voices

# basic examples
echo "hello mr streamer" | tts
tts 'O, o. .O, o.'
tts -v Emma 'what?'  # use a different voice

# save to filepath, and play after its downloaded. uses paplay, but mpv/vlc could also be used
echo 'Does this work? NO? .OK.' | tts -d /tmp/sound.ogg && paplay /tmp/sound.ogg
```

## Notes

Converted to a nicer interface from the one liner found [here](https://gist.github.com/idealwebsolutions/84dcb061baa427050672b9b41f900ce8#comments).

Disclaimer: Not affiliated or endorsed by StreamLabs

