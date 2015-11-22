# Basic preferences for my user account on *nix systems

## Vim

Edit ~/.vimrc with the following:

       " binary resets some stuff, so set it first
        " no eol after last line
        set binary noeol
        
        " color syntax
        syntax on
        
        " tab is four spaces, space chars
        set tabstop=4
        set shiftwidth=4
        set expandtab
        
        " show ruler
        set ruler
        
        " highlight search pattern
        set hlsearch 


## GIT

Put the git-completions.sh and git-prompt.sh scripts in your PATH, for example ~/bin

        https://github.com/git/git/blob/master/contrib/completion/git-completion.bash
        https://github.com/git/git/blob/master/contrib/completion/git-prompt.sh

On OS X it is probably a good idea to use a global ignore file.


Located at: 

        .gitignore_global


With Content:

       .DS_Store


And include this block in your ~/.gitconfig

        [core]
            excludesfile = ~/.gitignore_global


## PROMPT Preferences

Add somethign like the following to your ~/.bash_profile

        # Enable tab completion
        source ~/bin/git-completion.bash
        
        # colors!
        green="\[\033[0;32m\]"
        blue="\[\033[0;34m\]"
        purple="\[\033[0;35m\]"
        reset="\[\033[0m\]"
        
        # Change command prompt
        source ~/bin/git-prompt.sh
        export GIT_PS1_SHOWDIRTYSTATE=1
        # '\u' adds the name of the current user to the prompt
        # '\$(__git_ps1)' adds git-related stuff
        # '\W' adds the name of the current directory
        export PS1="$purple\u$green\$(__git_ps1)$blue \W $ $reset"

## Terminal Preferences

The provided "title" script is useful for labeling an open terminal. Add to PATH, for example ~/bin

        See: bin/title


