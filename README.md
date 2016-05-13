# flack

i wrote a quick cue/flac splitting wrapper script in bash because
[split2flac](https://github.com/ftrvxmtrx/split2flac) was giving me weird path
issues. i wanted something with tolerable defaults.

# what it does

it just recurses thru every subdirectory looking for cue files, then tries to
split a flac file with the same name in the same subdirectory, using some
[ok defaults](unix.stackexchange.com/questions/10251/how-do-i-split-a-flac-with-a-cue). then
it tags them from the flac track info.

so if you have a lot of files that look like
`music/big_flac_album/big_flac_album.cue` and
`music/big_flac_album/big_flac_album.flac`, you will get a lot of folders that
look like `music/big_flac_album/split/big_flac_album/01-first-flac-track.flac`.

at this point it then converts all of them to variable bitrate AAC.

# dependencies

- shntool
- cuetools
- flac
- libav

# how to use

1. copy [script](./flack) to someplace on your `$PATH`, or a directory where you
   want to use it--anywhere above your big FLAC/CUE pairs is fine
2. install dependencies: `brew install DEPENDENCY` or `apt-get install
   DEPENDENCY`
2. `chmod +x flack`
3. ./flack
4. wait
5. relax
