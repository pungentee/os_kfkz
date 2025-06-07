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

### 6. Schedule Events and Calendar — **calcurse**

```bash
calcurse
```

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

Key controls:

- Space/n - next image
- Backspace/p - previous image
- +/- - zoom in/out
- f - fullscreen toggle
- q - quit

## Task 2.

## Task 3.

## Conclusion
