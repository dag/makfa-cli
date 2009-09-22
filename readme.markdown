Command-line makfa
==================

Lojban dictionary. Beta!

Install
-------

    su -c 'wget -O /usr/bin/makfa http://github.com/dag/makfa-cli/raw/master/makfa; chmod +x /usr/bin/makfa'

Maybe:

    su -c 'ln -s makfa /usr/bin/m'

The first run is slow as it downloads the dictionary.
Not to worry, the next run will be blazing fast!

Usage
-----

The `find` command dumps out matching entries, the `show` command shows all known information.
The `console` command combines these two with a readline prompt.
All other commands are like `show` but for specific information.
All commands take a `-h` or `--help` switch for option listings.
All display commands except `show` take a `-q` or `--quiet` switch to only show the specifically requested information.
All display commands take a list of entries either as arguments or on standard input.
Unambiguous command initials are expanded.

So what does all this mean?

It is script and pipe friendly:

    $ m f -D | shuf | head -5
                        cuxna : x1 chooses/selects x2 [choice] from set/sequence of alternatives x3 (complete set).
                         su'i : n-ary mathematical operator: plus; addition operator; [(((a + b) + c) + ...)].
                     mo'ica'u : space motion tense: forward directional space motion.
                         de'a : event contour for a temporary halt and ensuing pause in a process.
                      su'anai : evidential: I generalize - I particularize; discursive: abstractly - concretely.

All the space is aligning with the longest registered word.
You can also use command substition or backticks:

    $ makfa show $(makfa find | shuf | head -2)
                       piksku : lujvo
                              : c1=p3 (agent) comments/remarks on/observes c2=p1 about subject x3=p2 to audience x4=c3=p4 via expressive medium x5=c5.
                              : (x1) "remark" in the sense of "express a comment", "observe" in the sense of "express a comment", "comment" in the sense of "express a comment"
                              : Cf. {zgana}, {ga'a}, {za'a}, {retsku}.

                        palne : gismu
                              : x1 is a tray/platter/flat container [pan/sheet/griddle] of contents x2, and made of material x3.
                              : (x1) "tray"
                              : Also pallet, when used for carrying rather than support on the ground; a tray is flat-bottomed and shallow or without a rim, and is generally portable.  See also {tansi}, {patxu}, {palta}, {ckana}.

It provides shortcuts for common combinations:

    $ m f -Dsui4
                         re'e : emotion category/modifier: religious/spiritual/worship - sacrilege.
                         ro'a : emotion category/modifier: social - antisocial.
                         ro'e : emotion category/modifier: mental - mindless.
                         ro'i : emotion category/modifier: emotional - denying emotion.
                         ro'o : emotion category/modifier: physical - denying physical.
                         ro'u : emotion category/modifier: sexual - sexual abstinence.

If you want to update the dictionary:

    rm ~/.makfa.dump

