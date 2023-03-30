# alpha60
Sources for bittorrent swarm analysis tools. With another repository of [static data] (https://github.com/bdekoz/alpha60-data), and a directory or directories of seralized sample results, is able to cache, analyze, and render results for the sampled peer behaviour in a variety of output views and image formats.

[Source Documentation](https://bdekoz.github.io/alpha60-docs/)



**PREREQUISITES**

Development and use is hosted on top-of-tree Linux. At the moment,
this means Fedora 34 or Centos 8 operating systems on multi-core
x86_64 hardware.

Some familiarity with Linux, GNU coding styles, C++17-21, and the Bittorrent
protocol are assumed.

Detailed notes on setting up the development and sampling environment can be found [here] (https://sunglint.wordpress.com/?s=bittorrent).

**BUILDING**

Main excecutables are built from sources in the src directory, by running `scripts/compile.sh` like so
```
../scripts/compile-source.sh a60-btiha-check.cc
```

**RUNNING**

```
a60-btiha-check.exe 

a60-sample-dump-multi.exe
a60-cache-samples.exe
a60-cache-recache-synthesize-uniques.exe
a60-sample-analyze.exe

a60-metadata-analyze.exe
a60-metadata-query.exe
```

Methods (as compiled into executables) should be run in the sequence as above.

`a60-btiha-check.exe torrent-file-directory`

Validity checks for the whole BTIHA: a *torrent collection* composed of a set of torrent and magnet files located in *torrent-file-directory*. Output is a list of ill-formed input files, and a list of torrent files with duplicate BTIH arrays. Can rename filenames to BTIH value.


`a60-sample-dump-multi.exe torrent-file-directory output-directory`

Samples a *torrent collection* composed of a set of torrent and magnet files located in *torrent-file-directory* according to a pre-determined timer setup in the file itself. Output JSON files are saved in *per-date* and *per-hour* directores nested in *output-directory*.

`a60-cache-samples.exe sample-directory persistent-cache-directory`

Transforms sample JSON to re-written JSON files quantized via *hour*, *day*, *week*, and *cumulative* durations. Can be made *incremental* via awareness of previously computed cache files and is thus *restartable*. Persistent output JSON files are optionally saved in *persistent-cache-directory*. Configurable as which specific quanta to cache.

`a60-sample-analyze.exe cache-directory`

Transforms cache JSON to SVG visual forms. These forms are output into the *cache-directory*. The SVG files can be transformed into various other formats (PNG, PDF, MKV) via scripts.
