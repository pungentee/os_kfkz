## Work Case №4

### Task 1. During your work, you often need to install new programs and applications. 

### Task 2. Identify which package manager your Linux distribution uses.

### Task 3. Install the packages using the package manager on your terminal.

To instal the audio player package (VLC in our case) we need to use the command `emerge`, part of the package manager Portage.

Before installing the package we need to update the local database by running 

```
emerge --sync
```

To install vlc package we need to execute 

```
emerge --ask --verbose vlc
```

Explanation:

- `--ask` flag is used to emerge command to ask the user `Would you like to merge this packages?`. 
- `--verbose` flag is used to pack. manager display more logs while compiling package.

To install the development environment, that I prefer, we need to execute following command:

```
emerge --ask --vebose app-editors/neovim
```

Explanation:

I used the full-path of the package in the repository to portage correctly determine which package I wanted to install.
