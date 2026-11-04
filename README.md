# AVL Drumkits, laid out for strudel and benny

Five sample kits by **Glen MacArthur** ([AV Linux](http://www.bandshed.net/avldrumkits/), "AVL Drumkits", 2015),
arranged as a strudel sample library: one folder per piece, a `strudel.json` at the root.

| kit | sounds start with | what it is |
|---|---|---|
| Black Pearl (the x42 plugin's "Captain's Kit") | `avl_pearl_` | Pearl acoustic kit, Sabian and Zildjian cymbals |
| Blonde Bop (x42 "Goldibops") | `avl_blondebop_` | TAMA jazz kit |
| Blonde Bop HR (x42 "Goldibops", second variant) | `avl_blondebophr_` | the same kit, hot rod snare variant |
| Red Zeppelin (x42 "Led Head") | `avl_redzep_` | Ludwig rock kit |
| Buskman's Holiday (x42 "Busk Stop") | `avl_buskman_` | cajon, congas, shakers, hand percussion |

Every piece is in `PIECES.md` (its sound name, its original name and General MIDI key, its layer count, its original pan and choke group).

## Using it

In strudel: `samples('github:playbenny/avl-drumkits-strudel')`, then for example
`s("avl_pearl_kick avl_pearl_snare avl_pearl_hat_closed avl_pearl_snare").velocity(.8)` or
`n("0 1 2 3 4").s("avl_pearl_snare")` to step through the five layers by hand.
In benny it is a bundled remote library.

Most pieces have five velocity layers (Buskman's Holiday has ten), chosen by MIDI velocity in the
original. Each layer's central velocity is in its file name (`avl_pearl_snare_vel065.wav`); benny reads that and
switches layers exactly where the original SFZ did (the softest layer also answers velocity 0). Stock strudel
sees the layers as the sound's variations in order, softest first. A piece with one sample (the cymbal chokes) has none.

## What was changed

**The samples are unchanged.** They are the original 44.1 kHz, 16-bit mono recordings from the SFZ releases at
bandshed.net, with no normalising, resampling, trimming or gain change. The only changes:

- the WAV files are byte-for-byte the originals (checked, every file);
- the files are renamed and put in folders by piece, with the velocity in the name;
- the SFZ's pan, choke groups and key map are not carried (strudel has no use for them; `PIECES.md` records them).

## Credit and licence

AVL Drumkits, created by Glen MacArthur, 2015. Website: http://www.bandshed.net/avldrumkits/ (contact info@bandshed.net).
Licensed **Creative Commons Attribution-ShareAlike 3.0** (`LICENSE`), with the author's exception, quoted from his readme:

> CC-BY-SA with the following exception: The by-sa condition is imperative if you modify the samples themselves or create
> new sample libraries with this licensed product. However, produced music and other non-sample-library works can be
> licensed freely. Attribution means keeping all authors information and this readme-file or its content in the release.
> If you want to create a fork, a modified version, of this sample library you have to release and distribute it under a
> different name.

This repository is released under a different name for that reason. Music you make with these sounds is yours to license as you like.
The LV2 plugin that plays them as SF2 files is [x42 avldrums.lv2](https://github.com/x42/avldrums.lv2) by Robin Gareus; this
repository does not contain it.

A pattern for each kit is in `examples.strudel`.
