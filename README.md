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

# dependencies

- shnsplit
- cuetools
- flac
