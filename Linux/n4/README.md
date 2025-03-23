## Work Case №4

### Task 1. During your work, you often need to install new programs and applications. 

### Task 2. Identify which package manager your Linux distribution uses.

Fedora uses the DNF (Dandified YUM) package manager.

### Searching for Packages

```bash
# Search for packages by name
dnf search firefox

# Search for packages by keyword in descriptions
dnf search all "web browser"

# Get more information about a specific package
dnf info firefox
```

### Installing Packages

```bash
# Install a packages from default repositories
sudo dnf install firefox gimp vlc

# Install a specific package version
sudo dnf install firefox-98.0.2

# Install a local RPM file
sudo dnf install ./package-name.rpm
```

### Adding New Repositories

```bash
# Add a repository using a repo file
sudo dnf config-manager --add-repo=https://repo.example.com/example.repo

# Enable a pre-configured but disabled repository
sudo dnf config-manager --set-enabled rpmfusion-free

# Install packages from specific repositories
sudo dnf --enablerepo=rpmfusion-nonfree install package-name
```

### Viewing Package Information

```bash
# List all installed packages
dnf list installed

# List all available packages
dnf list available

# List all packages in a specific repository
dnf repository-packages fedora list

# Check for package updates
dnf check-update

# See package dependencies
dnf repoquery --requires --resolve firefox
```

### Uninstalling Packages

```bash
# Remove a package
sudo dnf remove firefox

# Remove a package and its dependencies (if not needed by other packages)
sudo dnf autoremove firefox

# Remove orphaned packages (no longer needed dependencies)
sudo dnf autoremove
```

### Updating Packages

```bash
# Update repository metadata
sudo dnf makecache

# Update all packages
sudo dnf update

# Update specific package
sudo dnf update firefox

# Update the DNF package manager itself
sudo dnf update dnf
```

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
