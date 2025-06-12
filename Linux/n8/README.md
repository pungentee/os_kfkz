# Work Case #8

## Task 1. Terminal Tools

### Installation Commands

```bash
sudo dnf install ranger w3m mutt cmus transmission-cli calcurse feh tmux
```

### 1. Browse Files and Folders — **ranger**

```bash
ranger
```

![image](./attachments/ranger.png)

Key controls:

- /k or ↑/↓ — navigate up/down
- h/l or ←/→ — go back/forward directories
- Enter — open file/enter directory
- Space — select file
- q — quit
- ? — help

### 2. Browse Web Pages — **w3m**

```bash
w3m https://www.google.com
```

![image](./attachments/web.png)

Key controls:

- j/k or ↑/↓ — scroll up/down
- h/l or ←/→ — go back/forward
- Enter — follow link
- / — search
- q — quit

### 3. View Email — **mutt**

```bash
echo "set imap_url = 'imaps://username@imap.gmail.com:993/'" >> ~/.muttrc
echo "set imap_user = 'your-email@gmail.com'" >> ~/.muttrc
echo "set imap_pass = 'your-app-password'" >> ~/.muttrc
echo "set smtp_url = 'smtps://username@smtp.gmail.com:465/'" >> ~/.muttrc
echo "set smtp_user = 'your-email@gmail.com'" >> ~/.muttrc
echo "set smtp_pass = 'your-app-password'" >> ~/.muttrc
echo "set from = 'your-email@gmail.com'" >> ~/.muttrc
echo "set realname = 'Your Name'" >> ~/.muttrc

mutt
```

![image](./attachments/mutt.webp)

Key controls:

- j/k – navigate emails
- Enter – read email
- m – compose new email
- r – reply
- d – delete
- q – quit

### 4. Listen to Music — **cmus**

```bash
cmus
```

![image](./attachments/music.png)

Key controls:

- c — pause/play
- b — next track
- z — previous track
- s — stop
- `+` — volume up
- `-` — volume down
- q — quit

### 5. Download Torrents — **transmission-cli**

```bash
transmission-cli /path/to/file.torrent
```

![image](./attachments/torrent.png)

### 6. Schedule Events and Calendar — **calcurse**

```bash
calcurse
```

![image](./attachments/tasks.png)

Key controls:

- Tab — switch between calendar and todo
- a — add appointment
- t — add todo item
- d — delete selected item
- e — edit selected item
- s — save and quit
- q — quit without saving
- +/- — next/previous day
- Enter — view appointment details

### 7. View Images — **feh**

```bash
feh image.jpg
```

![image](./attachments/image.png)

Key controls:

- Space/n - next image
- Backspace/p - previous image
- +/- - zoom in/out
- f - fullscreen toggle
- q - quit

## Task 2.

### 1. Entering, Editing, and Deleting Text

#### Common text editors:

- `vi` / `vim` — terminal-based text editor, very popular and powerful  
- `nano` — easy-to-use terminal editor, user-friendly for beginners  
- `emacs` — highly extensible and powerful editor  
- `gedit` — graphical text editor for GNOME desktop environment  

#### Installing and using `vim` (usually pre-installed):

```bash
sudo apt-get update
sudo apt-get install vim
````

To edit a file with `vi`:

```bash
vi filename.txt
```

**Basic `vi` commands:**

* Press `i` to enter insert mode (start editing)
* Press `Esc` to exit insert mode
* Type `:w` and press Enter to save changes
* Type `:q` and press Enter to quit
* Type `:wq` and press Enter to save and quit
* Type `:q!` and press Enter to quit without saving

### 2. Monitoring Processes and System Resources

#### Common tools:

* `top` — terminal-based real-time system monitor
* `htop` — improved interactive process viewer (not always installed by default)
* `ps` — snapshot of current processes
* `glances` — advanced system monitoring tool
* `gnome-system-monitor` — graphical system monitor for GNOME desktop

#### Installing and using `htop`:

```bash
sudo apt-get update
sudo apt-get install htop
```

To start `htop`:

```bash
htop
```

`htop` provides:

* Real-time CPU and memory usage
* List of running processes with user, CPU%, memory%, and process tree
* Interactive process management (kill, renice)


## Task 3.

## Conclusion
