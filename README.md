# ffmpeg-cat

Concatenate multiple video files using the familiar `cat` syntax

## Introduction

This utility concatenates multiple video files using the familiar
`cat _input1_ _input2_ _input3_... > _output_` command syntax.
It is designed to make concatenation of pre-splitted similar spec
files(e.g. dash cam recordings) easier for regular users that don't
want other fancy features.

## Dependencies

* A recent Bash script interpreter that has a proper `nounset`
  inplementation(>=4.3)
* FFmpeg that has the following feature built-in:
    + The `concat` demuxer
    + Matroska container format support

## Installation

You should be able to run the [`ffmpeg-cat` program](ffmpeg-cat)
directly from the source tree.

[An official snap package](https://snapcraft.io/ffmpeg-cat) has been
built to simplify installation and usage which can be prepared using
the following text terminal commands:

```sh
# Install the package
sudo snap install ffmpeg-cat

# If your input files lived in /media or /mnt connect the confinement
# plug to allow access
sudo snap connect ffmpeg-cat:removable-media
```

## Usage

This is a text-based program which should be run in a text terminal.

Common usage example(assuming that the program lives in your command
search PATHs):

    ffmpeg-cat _input_file1_ _input_file2_... > output.mkv

It should be easy to insert the input file arguments via simply
dragging the input files(assuming to be sorted in alphabetical order)
from a file manager to a text terminal emulator(like Konsole).

Note that currently only the Matroska container format(MKV) is
supported as the output file format, as it is more flexible on what
kind of video/audio streams it can encapsulate.  Support for other
media container formats can be implemented if there's significant
need for the feature.

### Environment variables that can customize the program's behavior

#### FFCAT_DROP_SRC_FILES

Whether to automatically remove the input files after a successful
conversion.

**Default value:** `false`  
**Supported values:** `false`, `true`

## Support

Refer the issue tracker for limited, community-based support:

<https://github.com/brlin-tw/ffmpeg-cat/issues>

Patches are welcome if you have the ability to fix it yourself.

## Licensing

This software is licensed under [the Creative Commons
Attribution-ShareAlike 4.0 International license](https://creativecommons.org/licenses/by-sa/4.0/deed.en).

Specialized, case-by-case licensing is also possible but may incurr a
price, please file an issue for discussion.
