# Work Case #7

## Task 1.

## Task 2.

## Task 3. Using Systemd Timers as an Alternative to the Cron

### Environment

- Operating System: **Fedora**
- Alternative Scheduler: **Systemd timers**

### Timer 1: Daily Cleanup of Temporary Files

Action: **Removes files in /tmp older than 7 days**

Script: `/usr/local/bin/cleanup.sh`

```sh
#!/bin/bash
find /tmp -type f -mtime +7 -exec rm -f {} \;
echo "Cleanup completed at $(date)"
```

Service File: `/etc/systemd/system/cleanup.service`

```ini
[Unit]
Description=Cleanup temporary files

[Service]
ExecStart=/usr/local/bin/cleanup.sh
StandardOutput=journal
StandardError=journal
```

Timer File: `/etc/systemd/system/cleanup.timer`

```ini
[Unit]
Description=Run cleanup daily at 2 a.m.

[Timer]
OnCalendar=*-*-* 02:00:00
Persistent=true

[Install]
WantedBy=timers.target
```

### Timer 2: Weekly Directory Backup

Action: **Backs up `/home/user/documents` to `/backup/documents.tar.gz`**

Script: `/usr/local/bin/backup.sh`

```sh
#!/bin/bash
tar -czf /backup/documents.tar.gz /home/user/documents
echo "Backup completed at $(date)"
```

Service File: `/etc/systemd/system/backup.service`

```ini
[Unit]
Description=Backup documents

[Service]
ExecStart=/usr/local/bin/backup.sh
StandardOutput=journal
StandardError=journal
```

Timer File: `/etc/systemd/system/backup.timer`

```ini
[Unit]
Description=Run backup weekly on Sunday at 4 a.m.

[Timer]
OnCalendar=Sun *-*-* 04:00:00
Persistent=true

[Install]
WantedBy=timers.target
```

### Timer 3: Daily Update Check

Action: **Checks for system updates using dnf**

Script: `/usr/local/bin/update.sh`

```sh
#!/bin/bash
dnf check-update
echo "Update check completed at $(date)"
```

Service File: `/etc/systemd/system/update.service`

```ini
[Unit]
Description=Check for system updates

[Service]
ExecStart=/usr/local/bin/update.sh
StandardOutput=journal
StandardError=journal
```

Timer File: `/etc/systemd/system/update.timer`

```ini
[Unit]
Description=Run update check daily at 3 a.m.

[Timer]
OnCalendar=*-*-* 03:00:00
Persistent=true

[Install]
WantedBy=timers.target
```

### Timer 4: Post-Reboot Log

Action: **Logs the system boot time after each reboot**

Script: `/usr/local/bin/boot.sh`

```sh
#!/bin/bash
echo "System booted at $(date)"
```

Service File: `/etc/systemd/system/boot.service`

```ini
[Unit]
Description=Log boot time

[Service]
ExecStart=/usr/local/bin/boot.sh
StandardOutput=journal
StandardError=journal
```

Timer File: `/etc/systemd/system/boot.timer`

```ini
[Unit]
Description=Run after boot

[Timer]
OnBootSec=0

[Install]
WantedBy=timers.target
```

### Enabling and Starting the Timers

```sh
sudo systemctl enable cleanup.timer
sudo systemctl start cleanup.timer
sudo systemctl enable backup.timer
sudo systemctl start backup.timer
sudo systemctl enable update.timer
sudo systemctl start update.timer
sudo systemctl enable boot.timer
sudo systemctl start boot.timer
```

### Verifying and Monitoring

- List timers: `systemctl list-timers`

    ![image](./attachments/image3.1.png)

- Check status: `systemctl status <timer-name>.timer`

    ![image](./attachments/image3.2.png)

- View logs: `journalctl -u <service-name>.service`

    ![image](./attachments/image3.3.png)

## Conclusion

Task schedulers automate routine tasks in operating systems. We compared Windows Task Scheduler with Linux's Cron, which uses crontab files, and explored Systemd timers as a modern alternative. On Fedora, we scheduled daily cleanups, weekly backups, daily update checks, and post-reboot logging using Systemd timers. While Cron is simple and widely used, Systemd timers offer better integration, logging, and dependency management. The choice depends on system needs and user preferences.
