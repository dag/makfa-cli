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

    $ m f -sui4 | m d    # makfa find --selmaho UI4 | makfa definition
    re'e : emotion category/modifier: religious/spiritual/worship - sacrilege.
    ro'a : emotion category/modifier: social - antisocial.
    ro'e : emotion category/modifier: mental - mindless.
    ro'i : emotion category/modifier: emotional - denying emotion.
    ro'o : emotion category/modifier: physical - denying physical.
    ro'u : emotion category/modifier: sexual - sexual abstinence.

    $ m g $(m f -sui4)   # makfa gloss $(makfa find --selmaho UI4)
    re'e : "spiritual"
    ro'a : "social"
    ro'e : "mental"
    ro'i : "emotional"
    ro'o : "physical"
    ro'u : "sexual"

If you want to update the dictionary:

    rm ~/.makfa.dump

