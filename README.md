# subtitle-delay

A program written in Python that directly edits SRT file to delay the subtitles.

Adapted for compatibility with subtitles in **Pt-BR**.

## What Changed:

+ Read/Write encodings replaced with **ISO 8859-1** (Latin-1) to allow proper handling of special characters in *Portuguese* subtitles.
+ Combined files into `delay.py` for easier use.

## Features:

1. Will throw an error if delaying with negative number pushes the initial time-stamp out of bounds.
2. Can delay subtitles in multiple SRT files at once.

## Installation:

```
git clone https://github.com/hesout/subtitle-delay.git
cd subtitle-delay
```

## Usage:

```Python
python delay.py srt_file_name delay_time
```

- `srt_file_name` must end with `.srt` extension
  - Additionally, `.` and `*` can be used instead of `srt_file_name` to delay the first (lexicographic) and all the SRT file(s) in the current working directory respectively.
- `delay_time` can be an integer or float with upto 3 digit precision, further precision will be dropped.

## Examples:

1.  Delaying subtitles in `subtitle.srt` by `3` seconds.

```Python
python delay.py subtitle.srt 3
```

2.  Delaying subtitles in the first `.srt` file in the directory ordered lexicographically by `-2` seconds.

```Python
python delay.py . -2
```

1.  Delaying the subtitles in all `.srt` files in current directory by `1.754` seconds.

```Python
python delay.py * 1.754
```
