
# Table of Contents

1.  [Homebrew tap: pgpb](#org8bc090e)
    1.  [Formulas](#org0d2dbc9)
        1.  [GnuPG 2.2.41](#org85668f6)
        2.  [Midnight Commander](#org498a81c)



<a id="org8bc090e"></a>

# Homebrew tap: pgpb

My personal [Homebrew tap](https://docs.brew.sh/How-to-Create-and-Maintain-a-Tap).


<a id="org0d2dbc9"></a>

## Formulas

To register a tap in Homebrew do:

    brew tap pgpbpadilla/pgpb 


<a id="org85668f6"></a>

### GnuPG 2.2.41

Background:

1.  After running an upgrade with `homebrew`, the package `gnupg`
    was upgraded to the latest stable version: 2.4
2.  `gnupg@2.4` introduces changes that breaks Emac's EasyPG:
    -   google: emacs org gpg hangs:
        <https://stackoverflow.com/q/76388376/400544>
    -   `BEGIN_ENCRYPTION` status output happens later in 2.4.1 (breaks
        Emacs's EasyPG): <https://dev.gnupg.org/T6481>
3.  In my private computer I was able to downgrade to 2.2.41, which
    made everything work, thanks to
    <https://stackoverflow.com/a/76404609/400544>
4.  a couple of weeks later, my work computer broke too, same
    scenario, `brew upgrade` installed `gnupg@2.4.1`
5.  uninstalled 2.4.1
6.  installed `brew install =gnupg@2.2`, however, this time the
    version installed was not 2.2.41 but 2.2.42 which is also
    broken
7.  since minor versions are not versioned formulas, i.e., they
    don't show when you do:
    
        brew search gnupg
    
        gnupg
        gnupg-pkcs11-scd
        gnupg@1.4
        gnupg@2.2
        pgpbpadilla/pgpb/gnupg@2.2.41
        gnu-go
8.  I ended up creating [this formula](Formula/gnupg@2.2.41.rb) to install `gnupg@2.2.41`


<a id="org498a81c"></a>

### Midnight Commander

This Homebrew tap started with the need to install of Midnight
Commander (MC) that is free from the bug described in [#4356: Subshell
returns to panels view on key press (any
key).](<http://midnight-commander.org/ticket/4356>)

****Beware that this tap will install a very old version of MC.****

To install MC, simply do:

    brew tap pgpbpadilla/pgpb brew info
    pgpbpadilla/pgpb/midnight-commander brew install
    pgpbpadilla/pgpb/midnight-commander

1.  Related

    1.  [midnight-commander#4356](http://midnight-commander.org/ticket/4356): Subshell returns to panels view on key
        press (any key)
    2.  [homebrew-core#97718](https://github.com/Homebrew/homebrew-core/issues/97718):\`midnight-commander\`: latest formula uses
        broken version 4.8.27

