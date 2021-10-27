# torrentfile

![torrentfile](https://github.com/alexpdev/torrentfile/blob/master/assets/torrentfile.png?raw=true)

------

## Bittorrent File Creator (.torrent)

[![Codacy Badge](https://app.codacy.com/project/badge/Grade/2da47ec1b5904538a40230f049a02be4)](https://www.codacy.com/gh/alexpdev/torrentfile/dashboard?utm_source=github.com&utm_medium=referral&utm_content=alexpdev/torrentfile&utm_campaign=Badge_Grade)
[![Codacy Badge](https://app.codacy.com/project/badge/Coverage/2da47ec1b5904538a40230f049a02be4)](https://www.codacy.com/gh/alexpdev/torrentfile/dashboard?utm_source=github.com&utm_medium=referral&utm_content=alexpdev/torrentfile&utm_campaign=Badge_Coverage)
![GitHub repo size](https://img.shields.io/github/repo-size/alexpdev/torrentfile?style=plastic)
![GitHub](https://img.shields.io/github/license/alexpdev/torrentfile?style=plastic)

_Torrentfile_ is a CLI for creating .torrent files for bittorrent clients.

## Features

- Simple interface
- Create meta files for Bittorrent v1
- Create meta files for Bittorrent v2
- Create Hybrid files for Bittorrent v1 & v2
- Create files with multiple trackers
- Check .torrent file for verifying download completed.
- Specify piece length attribute or let program calculate appropriate value.
- Flag torrent file as private for private trackers.
- Support for validating downloaded content from v1, v2, and hybrid file hashes.
- Optional GUI can be found at [https://github.com/alexpdev/TorrentfileQt](https://github.com/alexpdev/TorrentfileQt)

## Documentation

Documentation can be found by opening your webrowser in the `docs` directory
or by visiting [https://alexpdev.github.io/torrentfile](https://alexpdev.github.io/torrentfile).

## Installation

### via PyPi

`> pip install torrentfile`

### via Git

`> git clone https://github.com/alexpdev/torrentfile.git`

### download

Or download the latest release from the Release page on github.
[https://github.com/alexpdev/torrentfile/releases](https://github.com/alexpdev/torrentfile/releases)

## Using

     usage: torrentfile -v --version
            torrentfile -h --help
            torrentfile --checker <metafile> <content>
            torrentfile <path> [-o <dest>] [-a <url>] [-d] [--source <x>]
                        [--piece-length <n>] [--meta-version <n>] [--private]
                        [--announce-list <url2> <...>]  [--comment <comment>]


    Torrent file creator and checker for Bittorrent v1 & v2.  Supports .torrent files v1, v2 & combo/hybrid formats.

    positional arguments:
      <path>                                Path to file or directory containing .torrent file contents.

    optional arguments:
      -h, --help                            Show this help message and exit
      -v, --version                         Show program version and exit
      -d, --debug                           Trigger debug mode
      -a <url>, --announce <url>            Tracker announce URL

      -p <val>, --piece-length <val>        Number of bytes in each piece the file is split into.
                                            Number value must be a perfect power of 2; as such, Acceptable
                                            input values include: Numbers `14 - 35` (inclusive) or a full value
                                            that is a perfect power of 2 and lies between 16KB and 16MB.
                                            i.e. [--piece-length 14] is the same as [--piece-length  16384]
                                            Alternatively, leave blank and let the program calulate the
                                            appropriate piece length.

      --private                             Create file for use with private tracker.
      -o <dest>, --out <dest>               Output path where the .torrent file will be written.

      --meta-version <n>                    Options = 1, 2 or 3.
                                            (1) = Bittorrent v1;. (Default)
                                            (2) = Bittorrent v2.
                                            (3) = Bittorrent v1 & v2 hybrid.
                                            Specify the Bittorrent Protocol and
                                            formatting version for .torrent file.

      --comment <text>                      Include a comment in file metadata.
      --source <text>                       Specify source.
      --announce-list <url> [<url> ...]     Additional tracker announce URLs.

      --checker <path> <path>               Trigger torrent re-check mode.
                                            If this option is active, then all other options are ignored except debug.
                                            Reviews current files in directory, and provides a percentage of total
                                            torrentfile content that is available.
                                            Arguements: 1) Absolute or relative path to The path to a ".torrent" file.
                                                        2) Absolute or relative path to Torrent Contents

## License

Distributed under the GNU LGPL v3 license. See `LICENSE` for more information.

[https://github.com/alexpdev](https://github.com/alexpdev/)
