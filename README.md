# Powerline-Shell (portable)

_"A beautiful and useful prompt for your shell"_ made portable.

<p align=center><img src="https://github.com/IfGremlinThen/powerline-shell/blob/master/bash-powerline-screenshot.png"></p>

## Changes
I forked this project because installing it via `python-pip` was a huge pain in the ass.\
It did not survive OS migrations, and downloading it from repos would make it more difficult to maintain over time.

Now it exists and runs entirely within your `/home` folder.

### Requirements
Requires `python3`.\
Includes `argparse.py` (<a href="https://github.com/IfGremlinThen/powerline-shell/blob/master/LICENSE.PSF">LICENSE</a>).

## Installation
Just drop the powerline-shell folder into ./config and add the following to your `.bashrc` or `.bash_aliases`:

```
function _update_ps1() {
    PS1=$(PYTHONPATH=$HOME/.config/powerline-shell\
    python3 $HOME/.config/powerline-shell/powerline-shell.py $?); }

if [[ $TERM != linux && ! $PROMPT_COMMAND =~ _update_ps1 ]]; then
    PROMPT_COMMAND="_update_ps1; $PROMPT_COMMAND"; fi
```
### Uninstallation
To uninstall, just reverse the above steps.
