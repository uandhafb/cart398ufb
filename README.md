# sound-repository
Template of a sound repository for Strudel.

Requirements: 
- python3
- soundfiles

## Usage
Organize your sound files inside subfolders in the root. For example

```
.
├── kick
│   ├── kick-01.wav
│   ├── kick-02.wav
├── bass
│   ├── bass-roll-short.wav
│   ├── foyer-bass-roll.wav
├── guitar
│   ├── pastel-click.wav
│   ├── harsh-realm-guitar-goise.wav
├── noise
│   ├── white.wav
│   ├── brown.wav
│   ├── pink.wav

```



Generate a Strudel-compatible samples JSON map.

- From the repo root, run:

```
python3 generate_strudel_samples_json.py --root . --base https://your.cdn.example/location --output strudel.json
```

- `--base` sets the URL prefix stored under `_base` in the JSON; leave it empty for local file use. If using Github, you should add your the repo Github address in the form `github:<user>/<repo>/<branch>`. For example: 
 `github:tidalcycles/dirt-samples`
- If you omit branch (like above), the `main` branch will be used.
- The generated `strudel.json` maps each sample folder to its audio files for Strudel or any sampler that reads the same format.
