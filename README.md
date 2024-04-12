### Project Status

This was always using an undocumented API, seems that the underlying APIs have changed so this no longer works. The endpoint used to be at <https://streamlabs.com/polly/speak>, if anyone knows if there's an updated URL feel free to open an issue.

# tts

A CLI tool to interact with the [StreamLabs](https://streamlabs.com/) Text-To-Speech API endpoint.

## Usage

```
Usage:  tts [-h] [-v VOICE] [-d FILENAME|-p] <text_to_speak>...
Converts text to speech using the StreamLabs API
Any other positional arguments are interpreted as the text input
If no text is present, reads from STDIN

   -h           Prints this help message and exits
   -v VOICE     Change the voice used for TTS
   -l           List available voices
   -d FILENAME  Download the .mpeg file to FILENAME.mpeg [default]
   -p           Instead of downloading, print the audio URL

Disclaimer: Not affiliated with or endorsed by StreamLabs
```

## Install

After installing [`curl`](https://github.com/curl/curl) and [`jq`](https://stedolan.github.io/jq/download/);

Download the `tts` script somewhere onto your `$PATH`

`wget -P ~/.local/bin 'https://raw.githubusercontent.com/seanbreckenridge/tts/master/tts' && chmod +x ~/.local/bin/tts`

Could also use [`basher`](https://github.com/basherpm/basher):

```bash
basher install seanbreckenridge/tts
```

## Examples

```
tts -l  # to list voices

# basic examples
echo "hello mr streamer" | tts
tts 'O, o. .O, o.'
tts -v Emma 'what?'  # use a different voice

# save to filepath, and play after its downloaded. uses paplay, but mpv/vlc could also be used
echo 'Does this work? NO? .OK.' | tts -d /tmp/sound.mpeg && plaympeg /tmp/sound.mpeg
```

Audio: <https://sean.fish/p/sound.mpeg>

## Notes

Converted to a nicer interface from the one liner found [here](https://gist.github.com/idealwebsolutions/84dcb061baa427050672b9b41f900ce8#comments).

Disclaimer: Not affiliated with or endorsed by StreamLabs
