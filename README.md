# Powerline-Shell (portable)

_"A beautiful and useful prompt for your shell"_ made portable.

<p align=center><img src="https://github.com/IfGremlinThen/powerline-shell/blob/master/bash-powerline-screenshot.png"></p>

## Changes
I forked this project because installing it via `python-pip` was a huge pain in the ass.\
It did not survive OS migrations and downloading it from repos would make it more difficult to maintain over time.

Now it exists and runs entirely within your `/home` folder.

### Requirements
Requires `python3`.\
Includes `argparse.py` (<a href="https://github.com/IfGremlinThen/powerline-shell/blob/master/LICENSE.PSF">LICENSE</a>).

## Installation
1.) Extract the contents of the archive,\
2.) rename the resulting folder to `powerline-shell`,\
3.) drag-and-drop `powerline-shell` into your ~/.config folder,\
4.) add the following lines to the bottom of your `.bashrc` or `.bash_aliases` files:
```
function _update_ps1() {
    PS1=$(PYTHONPATH=$HOME/.config/powerline-shell\
    python3 $HOME/.config/powerline-shell/powerline-shell.py $?); }

if [[ $TERM != linux && ! $PROMPT_COMMAND =~ _update_ps1 ]]; then
    PROMPT_COMMAND="_update_ps1; $PROMPT_COMMAND"; fi
```
To uninstall, just reverse steps 3 & 4.

## Customization
The `powerline-shell` folder includes a `config.json` for you to edit.  You can consult the <a href="https://github.com/IfGremlinThen/powerline-shell/blob/master/OLDREADME.md">OLDREADME</a> for more info.
