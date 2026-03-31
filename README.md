# flac-to-alac

A simple bash script to recursively convert a folder of FLAC files to ALAC (m4a) files.

## Installation (on macOS)

This has two system dependencies:

- `nq` - lightweight CLI queue utility
- `ffmpeg` - performs the lossless conversion

```sh
$ brew bundle install
```

Or install manually:

```sh
$ brew install ffmpeg nq
```

## Usage

```sh
$ ./flac-to-alac -i infolder -o outfolder
```

Example:

```sh
$ ./flac-to-alac -i "/Volumes/Lexar620/Music" -o "/Volumes/Lexar620/Music_ALAC"
```

## Behavior

- Recursively scans all `.flac` files under the input folder.
- Writes converted `.m4a` files to the output folder.
- Keeps relative subfolder structure in the output.
- Skips already valid output files so reruns are safe.
- Replaces zero-byte/broken outputs on rerun.

## Logs

- Converter log file: `$HOME/Library/Logs/flac-to-alac/info.log`
