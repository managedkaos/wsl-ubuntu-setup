# WSL Ubuntu Setup

Steps for setting up Ubuntu on WSL.

1. Download fonts to windows

    ```
    ./download_fonts.sh
    ```

1. Install fonts

    ```
    $fonts = (New-Object -ComObject Shell.Application).Namespace(0x14)
    Get-ChildItem -Recurse -include *.ttf | % { $fonts.CopyHere($_.fullname) }
    ```

1. Enable "no password" sudo

    ```
    echo "%${USER} ALL=(ALL) NOPASSWD:ALL" | sudo EDITOR='tee ' visudo --quiet --file=/etc/sudoers.d/passwordless-sudo
    ```


