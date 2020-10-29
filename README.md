# tts

A CLI tool to interact with the [StreamLabs](https://streamlabs.com/) Text-To-Speech API endpoint.

## Usage

```
Usage:  tts [-h] [-v VOICE] [-d FILENAME|-p] <text_to_speak>
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

- Install [`curl`](https://github.com/curl/curl) and [`jq`](https://stedolan.github.io/jq/download/)
- Download the `tts` script somewhere onto your `$PATH`:
  - manually: `wget -P ~/.local/bin 'https://raw.githubusercontent.com/seanbreckenridge/tts/master/tts' && chmod +x ~/.local/bin/tts`
  - or use [`sinister`](https://github.com/jamesqo/sinister) : `sh <(curl -sSL http://git.io/sinister) -u 'https://raw.githubusercontent.com/seanbreckenridge/tts/master/tts'`

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

Audio: <https://sean.fish/p/does_this_work.ogg>

## Notes

Converted to a nicer interface from the one liner found [here](https://gist.github.com/idealwebsolutions/84dcb061baa427050672b9b41f900ce8#comments).

Disclaimer: Not affiliated with or endorsed by StreamLabs
