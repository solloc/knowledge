# Git

## WinMerge as difftool on Windows

1. Locate .gitconfig file

    e.g. `C:\Users\<USER>\.gitconfig`

1. Add path to WinMerge UI

    ```
    ...
    [diff]
        tool = winmerge
    [difftool "winmerge"]
        cmd = "'C:/Program Files (x86)/WinMerge/WinMergeU.exe'" -e "$LOCAL" "$REMOTE"
    ...
    ```

Source: https://coderwall.com/p/76wmzq/winmerge-as-git-difftool-on-windows (2021)

## References

* [Merge unrelated histories](https://stackoverflow.com/a/47396921/2742174) (Stack Overflow 2017)
    
    `git pull origin master --allow-unrelated-histories`

* [Sign Commits at GitHub](https://docs.github.com/en/github/authenticating-to-github/managing-commit-signature-verification) with GPG Key