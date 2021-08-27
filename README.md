prompt-pwd
==========

Formats the path to the current working directory to be used by prompts.

Settings
--------

Use the following zstyle to enable truncating the path to the git root when in a git repo:

    zstyle ':zim:prompt-pwd' git-root yes

To customize the maximum number of characters per path component, use:

    zstyle ':zim:prompt-pwd:fish-style' dir-length 1

Setting the value to 0 will disable shortening entirely, which is the default behavior.

The default path separator is `/`, and it can be customized using:

    zstyle ':zim:prompt-pwd:separator' format '%F{magenta}/%f'

Theming
-------

Add a call to the `prompt-pwd` function in your prompt code where you want the current working
directory to be displayed. Here's an example:

```zsh
setopt nopromptbang prompt{cr,percent,sp,subst}

zstyle ':zim:prompt-pwd' git-root yes
zstyle ':zim:prompt-pwd' fish-style-dir-length 2
zstyle ':zim:prompt-pwd:separator' format '❯'

PS1='$(prompt-pwd)❯ '
```
