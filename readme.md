This is a clone of <https://gist.github.com/244215> of to provide ZSH integration with git.

Example usage in .zshrc, assuming this is checked out to `~/work/zsh-git`:

    # Autoload zsh functions.
    fpath=($fpath ~/work/zsh-git)
    autoload -U ~/work/zsh-git/*(:t)
     
    # Append git functions needed for prompt.
    preexec_functions+='preexec_update_git_vars'
    precmd_functions=(precmd_update_git_vars $precmd_functions)
    chpwd_functions+='chpwd_update_git_vars'
    
    # Use $(prompt_git_info) in your prompt and/or window title
