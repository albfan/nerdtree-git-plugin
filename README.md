nerdtree-git-plugin
===================
[![Build Status](https://travis-ci.org/albfan/nerdtree-git-plugin.svg?branch=master)](https://travis-ci.org/albfan/nerdtree-git-plugin)
[![Stories in Ready](https://badge.waffle.io/albfan/nerdtree-git-plugin.svg?label=ready&title=Ready)](http://waffle.io/albfan/nerdtree-git-plugin)

A plugin of NERDTree showing git status flags. Works with the **LATEST** version of NERDTree.

The original project [git-nerdtree](https://github.com/Xuyuanp/git-nerdtree) will not be maintained any longer.


![Imgur](http://i.imgur.com/jSCwGjU.gif?1)

## Installation

For Pathogen

`git clone https://github.com/albfan/nerdtree-git-plugin.git ~/.vim/bundle/nerdtree-git-plugin`

Now reload the `vim`

For Vundle

`Plugin 'scrooloose/nerdtree'`

`Plugin 'albfan/nerdtree-git-plugin'`

For NeoBundle

`NeoBundle 'scrooloose/nerdtree'`

`NeoBundle 'albfan/nerdtree-git-plugin'`

For Plug

`Plug 'scrooloose/nerdtree'`

`Plug 'albfan/nerdtree-git-plugin'`

## FAQ

> Got error message like `Error detected while processing function
177[2]..178[22]..181[7]..144[9]..142[36]..238[4]..NERDTreeGitStatusRefreshListener[2]..NERDTreeGitStatusRefresh:
line 6:
E484: Can't open file /tmp/vZEZ6gM/1` while nerdtree opening in fish, how to resolve this problem?

This was because that vim couldn't execute `system` function in `fish`. Add `set shell=sh` in your vimrc.

This issue has been fixed.

> How to config custom symbols?

Use this variable to change symbols.

	```vimscript
	let g:NERDTreeIndicatorMapCustom = {
	    \ "Modified"  : "✹",
	    \ "Staged"    : "✚",
	    \ "Untracked" : "✭",
	    \ "Renamed"   : "➜",
	    \ "Unmerged"  : "═",
	    \ "Deleted"   : "✖",
	    \ "Dirty"     : "✗",
	    \ "Clean"     : "✔︎",
        \ 'Ignored'   : '☒',
	    \ "Unknown"   : "?"
	    \ }
	 ```

> How to show `ignored` status?

`let g:NERDTreeShowIgnoredStatus = 1` (a heavy feature may cost much more time)

## testing

Test suite only need vim installed

    $ [pacman|apt-get|yum] install vim

Given that, you need to provide a failed test with three files:

 - testN.sh: bash script to generate scenario
 - testN.vim: source for vim where you do whatever operations in vim
 - testN.ok: Expected output for test

1. When reporting new issues, add `"""" failed` to testN.vim to allow suite to detect expected failed test
2. When fixing issues, remove failed mark to related test.

Please see files on t directory for examples

More info on [TDD](https://en.wikipedia.org/wiki/Test-driven_development)

### Running test suite

    $ cd t
    $ ./suite.sh


## Credits

*  [scrooloose](https://github.com/scrooloose): Open API for me.
*  [git_nerd](https://github.com/swerner/git_nerd): Where my idea comes from.
*  [PickRelated](https://github.com/PickRelated): Add custom indicators & Review code.
