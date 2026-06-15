# 🐧 Linux Commands — Complete Reference Guide

> A comprehensive reference for every distinct command found in your terminal history.
> Each command includes a description, syntax, flags, and practical examples.

---

## Table of Contents

### 📁 Commands from Your History (1–33)

| # | Command | Category |
|---|---------|----------|
| 1 | [`ls`](#1-ls--list-directory-contents) | Navigation & Files |
| 2 | [`cd`](#2-cd--change-directory) | Navigation |
| 3 | [`echo`](#3-echo--print-text-to-terminal) | Output & Redirection |
| 4 | [`cat`](#4-cat--concatenate--display-file-contents) | File Viewing |
| 5 | [`man`](#5-man--manual-pages) | Help & Documentation |
| 6 | [`mkdir`](#6-mkdir--make-directory) | File Management |
| 7 | [`mv`](#7-mv--move-or-rename-files) | File Management |
| 8 | [`cp`](#8-cp--copy-files-and-directories) | File Management |
| 9 | [`rm`](#9-rm--remove-files) | File Management |
| 10 | [`rmdir`](#10-rmdir--remove-empty-directory) | File Management |
| 11 | [`touch`](#11-touch--create-empty-files) | File Management |
| 12 | [`vim`](#12-vim--text-editor) | Editing |
| 13 | [`sudo`](#13-sudo--superuser-do) | Permissions & Security |
| 14 | [`apt` / `apt-get`](#14-apt--apt-get--package-manager) | Package Management |
| 15 | [`systemctl`](#15-systemctl--system-service-manager) | Services |
| 16 | [`history`](#16-history--command-history) | Shell |
| 17 | [`whoami`](#17-whoami--current-user) | User Info |
| 18 | [`exit`](#18-exit--exit-the-shell) | Shell |
| 19 | [`clear`](#19-clear--clear-the-terminal) | Shell |
| 20 | [`code`](#20-code--open-vs-code) | Development |
| 21 | [`htop`](#21-htop--interactive-process-viewer) | Process Management |
| 22 | [`ps`](#22-ps--process-status) | Process Management |
| 23 | [`kill`](#23-kill--terminate-processes) | Process Management |
| 24 | [`chmod`](#24-chmod--change-file-permissions) | Permissions |
| 25 | [`chown`](#25-chown--change-file-ownership) | Permissions |
| 26 | [`useradd`](#26-useradd--add-a-new-user) | User Management |
| 27 | [`userdel`](#27-userdel--delete-a-user) | User Management |
| 28 | [`passwd`](#28-passwd--change-user-password) | User Management |
| 29 | [`su`](#29-su--switch-user) | User Management |
| 30 | [`usermod`](#30-usermod--modify-a-user-account) | User Management |
| 31 | [`groupadd`](#31-groupadd--create-a-new-group) | Group Management |
| 32 | [`gpasswd`](#32-gpasswd--manage-group-memberships) | Group Management |
| 33 | [`groups`](#33-groups--show-group-memberships) | Group Management |

### 🆕 Essential Additional Commands (34–55)

| # | Command | Category |
|---|---------|----------|
| 34 | [`pwd`](#34-pwd--print-working-directory) | Navigation |
| 35 | [`find`](#35-find--search-for-files) | File Search |
| 36 | [`grep`](#36-grep--search-text-patterns) | Text Search |
| 37 | [`head`](#37-head--view-beginning-of-file) | File Viewing |
| 38 | [`tail`](#38-tail--view-end-of-file) | File Viewing |
| 39 | [`less`](#39-less--page-through-file-contents) | File Viewing |
| 40 | [`wc`](#40-wc--word-line-character-count) | Text Processing |
| 41 | [`sort`](#41-sort--sort-lines-of-text) | Text Processing |
| 42 | [`uniq`](#42-uniq--filter-duplicate-lines) | Text Processing |
| 43 | [`top`](#43-top--system-process-monitor) | Process Management |
| 44 | [`df`](#44-df--disk-free-space) | Disk & Storage |
| 45 | [`du`](#45-du--disk-usage) | Disk & Storage |
| 46 | [`free`](#46-free--memory-usage) | System Info |
| 47 | [`uname`](#47-uname--system-information) | System Info |
| 48 | [`hostname`](#48-hostname--system-hostname) | System Info |
| 49 | [`uptime`](#49-uptime--system-uptime) | System Info |
| 50 | [`id`](#50-id--user-identity-info) | User Info |
| 51 | [`which`](#51-which--locate-a-command) | Help & Documentation |
| 52 | [`wget`](#52-wget--download-files-from-web) | Networking |
| 53 | [`curl`](#53-curl--transfer-data-from-urls) | Networking |
| 54 | [`ping`](#54-ping--test-network-connectivity) | Networking |
| 55 | [`ssh`](#55-ssh--secure-shell-remote-login) | Networking |
| 56 | [`scp`](#56-scp--secure-copy-over-ssh) | Networking |
| 57 | [`tar`](#57-tar--archive-files) | Compression |
| 58 | [`ln`](#58-ln--create-links) | File Management |
| 59 | [`alias`](#59-alias--create-command-shortcuts) | Shell |
| 60 | [`export`](#60-export--set-environment-variables) | Shell |
| 61 | [`crontab`](#61-crontab--schedule-tasks) | Automation |
| 62 | [`journalctl`](#62-journalctl--view-system-logs) | Services |
| 63 | [`shutdown` / `reboot`](#63-shutdown--reboot--power-management) | System |
| 64 | [`Pipe & Redirection`](#64-pipe--redirection--operators) | Shell Operators |

---

## 📁 Navigation & File Management

---

### 1. `ls` — List Directory Contents

Lists files and directories in the current (or specified) directory.

**Syntax:**
```bash
ls [OPTIONS] [PATH]
```

**Common Flags:**

| Flag | Description |
|------|-------------|
| `-l` | Long format — shows permissions, owner, size, date |
| `-a` | Show all files including hidden (dotfiles) |
| `-la` | Long format + hidden files |
| `-lh` | Long format with human-readable sizes (KB, MB, GB) |
| `-lt` | Sort by modification time (newest first) |
| `-ltr` | Sort by modification time (oldest first) |
| `-R` | Recursive listing — includes subdirectories |
| `-lS` | Sort by file size (largest first) |
| `-f` | Do not sort; list in directory order |
| `-lf` | Long format, unsorted |

**Examples from your history:**
```bash
ls              # List files in current directory
ls -l foo       # Detailed list of files inside 'foo' directory
ls -lf          # Detailed listing without sorting
ls foo          # List contents of 'foo' directory
```

**Example output of `ls -l`:**
```
-rwxr-xr-- 1 dkjdi dkjdi  4096 Jun 15 10:30 abc.txt
drwxr-xr-x 2 dkjdi dkjdi  4096 Jun 15 10:30 foo/
```
> The columns are: permissions, link count, owner, group, size, date, name.

---

### 2. `cd` — Change Directory

Changes the current working directory.

**Syntax:**
```bash
cd [PATH]
```

**Common Usage:**

| Command | Description |
|---------|-------------|
| `cd ..` | Go up one directory level (parent directory) |
| `cd /` | Go to root directory |
| `cd ~` | Go to home directory |
| `cd -` | Go to the previous directory |
| `cd /etc` | Go to an absolute path |
| `cd foo` | Go to a relative path (subdirectory) |

**Examples from your history:**
```bash
cd ..                   # Move up one level
cd bin                  # Enter the 'bin' directory
cd etc                  # Enter the 'etc' directory
cd home/dkjdi/          # Navigate to a user's home directory
cd var                  # Enter the 'var' directory
cd log                  # Enter the 'log' directory
cd abs                  # Enter the 'abs' directory
cd daddy3               # Enter another user's home directory
```

> **Tip:** Use `cd` with no arguments to instantly return to your home directory (`~`).

---

### 3. `echo` — Print Text to Terminal

Prints text to standard output. Can also be used to write text into files using redirection.

**Syntax:**
```bash
echo [OPTIONS] "text"
```

**Common Flags:**

| Flag | Description |
|------|-------------|
| `-n` | Do not output a trailing newline |
| `-e` | Enable interpretation of escape sequences (`\n`, `\t`, etc.) |

**Redirection Operators:**

| Operator | Description |
|----------|-------------|
| `>` | Write output to a file (overwrites the file) |
| `>>` | Append output to a file (does not overwrite) |

**Examples from your history:**
```bash
echo "HEllo World"              # Print text to terminal
echo "HEllo World" > abc.txt    # Write text to abc.txt (creates/overwrites)
```

**More examples:**
```bash
echo "line 1" > file.txt        # Create file with content
echo "line 2" >> file.txt       # Append to file
echo -e "Hello\nWorld"          # Print on two lines
echo $HOME                      # Print value of HOME variable
```

---

### 4. `cat` — Concatenate & Display File Contents

Displays the contents of a file. Can also be used to concatenate multiple files.

**Syntax:**
```bash
cat [OPTIONS] [FILE...]
```

**Common Flags:**

| Flag | Description |
|------|-------------|
| `-n` | Number all output lines |
| `-b` | Number non-blank lines only |
| `-s` | Squeeze multiple adjacent blank lines into one |
| `-E` | Display `$` at end of each line |

**Examples from your history:**
```bash
cat abc.txt                     # Display contents of abc.txt
cat group                       # View the group file
cat /etc/passwd                 # View system user accounts
cat nginx/access.log            # View Nginx access logs
cat nginx/error.log             # View Nginx error logs
cat /etc/group                  # View system groups
```

**More examples:**
```bash
cat file1.txt file2.txt         # Concatenate and display two files
cat -n script.sh                # Display file with line numbers
cat > newfile.txt               # Create file and type content (Ctrl+D to save)
```

---

### 5. `man` — Manual Pages

Displays the manual/documentation for a command.

**Syntax:**
```bash
man [COMMAND]
```

**Navigation inside `man`:**

| Key | Action |
|-----|--------|
| `Space` | Next page |
| `b` | Previous page |
| `/pattern` | Search forward |
| `n` | Next search result |
| `q` | Quit |

**Examples from your history:**
```bash
man ls          # View the manual for 'ls'
man kill        # View the manual for 'kill'
```

**More examples:**
```bash
man man         # View the manual for 'man' itself
man -k search   # Search all man pages for the keyword "search"
man 5 passwd    # View section 5 (file formats) of passwd
```

---

### 6. `mkdir` — Make Directory

Creates one or more new directories.

**Syntax:**
```bash
mkdir [OPTIONS] DIRECTORY_NAME
```

**Common Flags:**

| Flag | Description |
|------|-------------|
| `-p` | Create parent directories as needed (no error if existing) |
| `-v` | Print a message for each created directory |
| `-m` | Set permissions mode (e.g., `mkdir -m 755 dir`) |

**Examples from your history:**
```bash
mkdir foo       # Create a directory called 'foo'
mkdir abs       # Create a directory called 'abs'
```

**More examples:**
```bash
mkdir -p a/b/c              # Create nested directories in one command
mkdir -v new_project         # Create directory and print confirmation
mkdir -m 700 private_dir     # Create directory with specific permissions
```

---

### 7. `mv` — Move or Rename Files

Moves files/directories to a new location, or renames them.

**Syntax:**
```bash
mv [OPTIONS] SOURCE DESTINATION
```

**Common Flags:**

| Flag | Description |
|------|-------------|
| `-i` | Prompt before overwriting |
| `-f` | Force move, overwrite without prompting |
| `-v` | Verbose — print each file being moved |
| `-n` | Do not overwrite an existing file |

**Examples from your history:**
```bash
mv abc.txt foo      # Move abc.txt into the 'foo' directory
```

**More examples:**
```bash
mv oldname.txt newname.txt      # Rename a file
mv file.txt /tmp/               # Move file to /tmp
mv -i *.log /backup/            # Move all .log files, prompt before overwrite
mv dir1/ dir2/                  # Move (rename) a directory
```

---

### 8. `cp` — Copy Files and Directories

Copies files or directories from one location to another.

**Syntax:**
```bash
cp [OPTIONS] SOURCE DESTINATION
```

**Common Flags:**

| Flag | Description |
|------|-------------|
| `-r` or `-R` | Copy directories recursively |
| `-i` | Prompt before overwriting |
| `-v` | Verbose — print files as they are copied |
| `-p` | Preserve file attributes (timestamps, permissions) |
| `-u` | Copy only when source is newer than destination |

**Examples from your history:**
```bash
cp abc.txt foo                              # Copy abc.txt into 'foo' directory
cp foo/abc.txt .                            # Copy file from foo to current directory
cp foo/abc.txt ..                           # Copy file from foo to parent directory
sudo cp index.html /var/www/html/index.html # Copy with root privileges
```

**More examples:**
```bash
cp -r project/ project_backup/     # Recursively copy entire directory
cp -v *.txt /backup/               # Copy all .txt files with verbose output
cp -p important.conf /etc/         # Copy preserving timestamps and permissions
```

---

### 9. `rm` — Remove Files

Deletes files (and optionally directories).

**Syntax:**
```bash
rm [OPTIONS] FILE...
```

**Common Flags:**

| Flag | Description |
|------|-------------|
| `-r` or `-R` | Remove directories and their contents recursively |
| `-f` | Force removal — ignore nonexistent files, never prompt |
| `-i` | Prompt before every removal |
| `-v` | Verbose — print each file being removed |

**Examples from your history:**
```bash
rm foo/abc.txt      # Remove abc.txt inside 'foo' directory
```

**More examples:**
```bash
rm file.txt                 # Delete a single file
rm -i important.txt         # Delete with confirmation prompt
rm -rf old_project/         # Force delete directory and all contents
rm -v *.log                 # Delete all .log files with verbose output
```

> ⚠️ **Warning:** `rm -rf /` can destroy your entire system. Always double-check paths!

---

### 10. `rmdir` — Remove Empty Directory

Removes **empty** directories only. Use `rm -r` for non-empty directories.

**Syntax:**
```bash
rmdir [OPTIONS] DIRECTORY
```

**Common Flags:**

| Flag | Description |
|------|-------------|
| `-p` | Remove directory and its empty parent directories |
| `-v` | Verbose — print a message for each directory removed |

**Examples from your history:**
```bash
rmdir foo       # Remove the empty 'foo' directory
```

**More examples:**
```bash
rmdir empty_dir                 # Remove an empty directory
rmdir -p a/b/c                  # Remove c, then b, then a (if all are empty)
rmdir -v test_folder            # Remove and confirm
```

---

### 11. `touch` — Create Empty Files

Creates an empty file or updates the timestamp of an existing file.

**Syntax:**
```bash
touch [OPTIONS] FILE...
```

**Common Flags:**

| Flag | Description |
|------|-------------|
| `-a` | Change only the access time |
| `-m` | Change only the modification time |
| `-c` | Do not create file if it doesn't exist |
| `-t` | Use a specified time instead of current time |

**Examples from your history:**
```bash
touch abc.txt       # Create an empty file called abc.txt
touch abctxt        # Create an empty file called abctxt
```

**More examples:**
```bash
touch file1.txt file2.txt file3.txt     # Create multiple files at once
touch -c existing.txt                    # Update timestamp only if file exists
touch -t 202301011200 file.txt           # Set specific timestamp
```

---

## ✏️ Text Editing

---

### 12. `vim` — Text Editor

A powerful, modal text editor for the terminal. It has different modes for inserting text, navigating, and issuing commands.

**Syntax:**
```bash
vim [FILE]
```

**Vim Modes:**

| Mode | How to Enter | Purpose |
|------|-------------|---------|
| Normal | Press `Esc` | Navigate, delete, copy, paste |
| Insert | Press `i`, `a`, or `o` | Type/edit text |
| Command | Press `:` in Normal mode | Save, quit, search/replace |
| Visual | Press `v` in Normal mode | Select text |

**Essential Commands:**

| Command | Description |
|---------|-------------|
| `:w` | Save the file |
| `:q` | Quit |
| `:wq` or `:x` | Save and quit |
| `:q!` | Quit without saving |
| `i` | Enter insert mode at cursor |
| `a` | Enter insert mode after cursor |
| `o` | Open new line below and enter insert mode |
| `dd` | Delete current line |
| `yy` | Copy (yank) current line |
| `p` | Paste after cursor |
| `u` | Undo |
| `Ctrl+r` | Redo |
| `/text` | Search forward for "text" |
| `:%s/old/new/g` | Replace all occurrences of "old" with "new" |
| `gg` | Go to beginning of file |
| `G` | Go to end of file |
| `:set number` | Show line numbers |

**Examples from your history:**
```bash
vim                                     # Open vim with no file
vim /var/www/html/index.html            # Edit a specific file
sudo vim /var/www/html/index.html       # Edit a file as root (for protected files)
```

---

## 🔐 Permissions & Superuser

---

### 13. `sudo` — Superuser Do

Runs a command with **root (superuser) privileges**. Required for system-level changes like installing packages, modifying system files, and managing users.

**Syntax:**
```bash
sudo [OPTIONS] COMMAND
```

**Common Flags:**

| Flag | Description |
|------|-------------|
| `-u USER` | Run command as a specific user (default is root) |
| `-i` | Start a root login shell |
| `-s` | Start a root shell without login |
| `-k` | Invalidate cached credentials (force re-authentication) |
| `-l` | List commands allowed for the current user |

**Examples from your history:**
```bash
sudo apt install nginx                          # Install a package as root
sudo apt update                                 # Update package lists
sudo apt upgrade                                # Upgrade installed packages
sudo cp index.html /var/www/html/index.html     # Copy file to protected path
sudo vim /var/www/html/index.html               # Edit a protected file
sudo useradd -m daddy3                          # Create a user
sudo userdel daddy3                             # Delete a user
sudo passwd daddy3                              # Set password for a user
sudo groupadd mygrp                             # Create a group
sudo usermod -aG mygrp dkjdi                    # Add user to a group
sudo chown messi abctxt                         # Change file ownership
```

> **Tip:** You will be prompted for **your own password** (not root's) when using `sudo`.

---

### 24. `chmod` — Change File Permissions

Changes the access permissions (read, write, execute) of a file or directory.

**Syntax:**
```bash
chmod [OPTIONS] MODE FILE
```

**Understanding Permission Numbers:**

Each digit represents permissions for **Owner**, **Group**, and **Others**:

| Number | Permission | Symbol |
|--------|-----------|--------|
| 0 | No permission | `---` |
| 1 | Execute only | `--x` |
| 2 | Write only | `-w-` |
| 3 | Write + Execute | `-wx` |
| 4 | Read only | `r--` |
| 5 | Read + Execute | `r-x` |
| 6 | Read + Write | `rw-` |
| 7 | Read + Write + Execute | `rwx` |

**Common Permission Patterns:**

| Mode | Meaning |
|------|---------|
| `777` | Everyone can read, write, and execute |
| `755` | Owner: full; Group/Others: read + execute |
| `750` | Owner: full; Group: read + execute; Others: none |
| `700` | Owner: full; Group/Others: none |
| `644` | Owner: read + write; Group/Others: read only |
| `400` | Owner: read only; all others: none |
| `000` | No permissions for anyone |

**Symbolic Mode:**

| Symbol | Meaning |
|--------|---------|
| `u` | User (owner) |
| `g` | Group |
| `o` | Others |
| `a` | All (user + group + others) |
| `+` | Add permission |
| `-` | Remove permission |
| `=` | Set exact permission |

**Examples from your history:**
```bash
chmod 000 dkjdi         # Remove ALL permissions
chmod 400 dkjdi         # Owner can read only
chmod 001 dkjdi         # Others can execute only
chmod 100 dkjdi         # Owner can execute only
chmod 750 dkjdi         # Owner: rwx, Group: r-x, Others: ---
chmod 777 abctxt        # Everyone: rwx (full access)
```

**More examples:**
```bash
chmod u+x script.sh             # Add execute permission for owner
chmod g-w file.txt              # Remove write permission for group
chmod o=r file.txt              # Set others to read-only
chmod -R 755 project/           # Recursively set permissions on a directory
```

---

### 25. `chown` — Change File Ownership

Changes the owner (and optionally the group) of a file or directory.

**Syntax:**
```bash
chown [OPTIONS] OWNER[:GROUP] FILE
```

**Common Flags:**

| Flag | Description |
|------|-------------|
| `-R` | Change ownership recursively (for directories) |
| `-v` | Verbose — print changes being made |
| `--reference=FILE` | Use the owner/group of another file |

**Examples from your history:**
```bash
sudo chown messi abctxt         # Change owner of abctxt to 'messi'
```

**More examples:**
```bash
sudo chown alice file.txt               # Change owner to alice
sudo chown alice:developers file.txt    # Change owner and group
sudo chown :staff file.txt              # Change only the group
sudo chown -R www-data:www-data /var/www/   # Recursively change ownership
```

---

## 📦 Package Management

---

### 14. `apt` / `apt-get` — Package Manager

The package manager for Debian/Ubuntu-based Linux systems. Used to install, update, upgrade, and remove software packages.

**Syntax:**
```bash
sudo apt [COMMAND] [PACKAGE_NAME]
sudo apt-get [COMMAND] [PACKAGE_NAME]
```

> `apt` is the modern, user-friendly version. `apt-get` is the older, script-friendly version.

**Common Commands:**

| Command | Description |
|---------|-------------|
| `sudo apt update` | Refresh the list of available packages from repositories |
| `sudo apt upgrade` | Upgrade all installed packages to the latest version |
| `sudo apt install PACKAGE` | Install a new package |
| `sudo apt remove PACKAGE` | Remove a package (keep config files) |
| `sudo apt purge PACKAGE` | Remove a package **and** its config files |
| `sudo apt autoremove` | Remove unused dependencies |
| `sudo apt search KEYWORD` | Search for packages by keyword |
| `sudo apt show PACKAGE` | Show detailed info about a package |
| `sudo apt list --installed` | List all installed packages |
| `sudo apt full-upgrade` | Upgrade packages, removing old ones if needed |

**Examples from your history:**
```bash
sudo apt update                 # Refresh package lists
sudo apt upgrade                # Upgrade all packages
sudo apt install nginx          # Install Nginx web server
sudo apt-get install            # (older syntax) Install packages
```

> **Tip:** Always run `sudo apt update` before `sudo apt install` to ensure you get the latest package versions.

---

## ⚙️ System Services

---

### 15. `systemctl` — System Service Manager

Controls **systemd** services — start, stop, restart, enable/disable services, and check their status.

**Syntax:**
```bash
systemctl [COMMAND] [SERVICE_NAME]
```

**Common Commands:**

| Command | Description |
|---------|-------------|
| `systemctl status SERVICE` | Show current status of a service |
| `systemctl start SERVICE` | Start a service |
| `systemctl stop SERVICE` | Stop a service |
| `systemctl restart SERVICE` | Restart a service |
| `systemctl reload SERVICE` | Reload config without restarting |
| `systemctl enable SERVICE` | Enable service to start at boot |
| `systemctl disable SERVICE` | Disable service from starting at boot |
| `systemctl is-active SERVICE` | Check if a service is running |
| `systemctl list-units --type=service` | List all services |

**Examples from your history:**
```bash
systemctl status nginx      # Check if Nginx is running
```

**More examples:**
```bash
systemctl start nginx           # Start Nginx
systemctl stop nginx            # Stop Nginx
systemctl restart nginx         # Restart Nginx
systemctl enable nginx          # Start Nginx automatically on boot
sudo systemctl daemon-reload    # Reload systemd after config changes
```

**Understanding status output:**
```
● nginx.service - A high performance web server
     Loaded: loaded (/lib/systemd/system/nginx.service; enabled)
     Active: active (running) since Sun 2026-06-15 10:00:00 UTC
```

---

## 🖥️ Shell & Terminal Utilities

---

### 16. `history` — Command History

Displays a numbered list of previously executed commands.

**Syntax:**
```bash
history [OPTIONS] [N]
```

**Common Usage:**

| Command | Description |
|---------|-------------|
| `history` | Show full command history |
| `history 20` | Show last 20 commands |
| `history -c` | Clear the history |
| `!N` | Re-run command number N (e.g., `!42`) |
| `!!` | Re-run the last command |
| `!string` | Re-run last command starting with "string" |
| `history \| grep "keyword"` | Search history for a keyword |

**Examples from your history:**
```bash
history         # Display full command history
```

---

### 17. `whoami` — Current User

Prints the username of the currently logged-in user.

**Syntax:**
```bash
whoami
```

**Example output:**
```bash
$ whoami
dkjdi
```

> **Related:** `id` shows UID, GID, and group memberships. `who` shows all logged-in users.

---

### 18. `exit` — Exit the Shell

Closes the current terminal session or shell.

**Syntax:**
```bash
exit [STATUS_CODE]
```

**Examples:**
```bash
exit        # Exit with status 0 (success)
exit 1      # Exit with status 1 (error)
```

> **Tip:** You can also press `Ctrl+D` to exit a shell session.

---

### 19. `clear` — Clear the Terminal

Clears all text from the terminal screen.

**Syntax:**
```bash
clear
```

> **Shortcut:** Press `Ctrl+L` to clear the screen without typing a command.

---

### 20. `code` — Open VS Code

Opens Visual Studio Code from the terminal.

**Syntax:**
```bash
code [OPTIONS] [PATH]
```

**Common Usage:**

| Command | Description |
|---------|-------------|
| `code .` | Open current directory in VS Code |
| `code file.txt` | Open a specific file |
| `code -n .` | Open in a new window |
| `code --diff file1 file2` | Compare two files |
| `code -r .` | Open in the most recently used window |

**Examples from your history:**
```bash
code .      # Open current directory in VS Code
```

---

## 📊 Process Management

---

### 21. `htop` — Interactive Process Viewer

An **interactive** process viewer and system monitor. It is an enhanced version of `top`.

**Syntax:**
```bash
htop [OPTIONS]
```

**Key Bindings inside htop:**

| Key | Action |
|-----|--------|
| `F1` or `h` | Help |
| `F2` or `S` | Setup/configuration |
| `F3` or `/` | Search for a process |
| `F4` or `\` | Filter processes |
| `F5` or `t` | Tree view |
| `F6` or `>` | Sort by column |
| `F9` or `k` | Kill a process |
| `F10` or `q` | Quit |
| `Space` | Tag/untag a process |
| `u` | Filter by user |
| `M` | Sort by memory usage |
| `P` | Sort by CPU usage |

**Example:**
```bash
htop        # Launch interactive process viewer
```

> **Note:** `htop` may need to be installed: `sudo apt install htop`

---

### 22. `ps` — Process Status

Displays currently running processes. Unlike `htop`, `ps` gives a snapshot (not interactive).

**Syntax:**
```bash
ps [OPTIONS]
```

**Common Flags:**

| Flag | Description |
|------|-------------|
| `-a` | Show processes from all users |
| `-u` | Show detailed user-oriented format |
| `-x` | Include processes without a controlling terminal |
| `-e` or `-A` | Show every process on the system |
| `-f` | Full format listing |
| `aux` | BSD-style: all processes, user-oriented, including backgrounded |

**Examples from your history:**
```bash
ps          # Show processes for current shell
ps -a       # Show processes from all users
```

**More examples:**
```bash
ps aux                      # Show all running processes (BSD-style)
ps -ef                      # Full format of all processes
ps aux | grep nginx         # Find nginx processes
ps -u dkjdi                 # Show processes owned by user 'dkjdi'
```

**Example output of `ps aux`:**
```
USER       PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND
root         1  0.0  0.1 169500 13256 ?        Ss   Jun15   0:03 /sbin/init
dkjdi     2774  0.0  0.0   5480  3120 pts/0    S+   10:30   0:00 vim
```

---

### 23. `kill` — Terminate Processes

Sends a signal to a process, usually to terminate it.

**Syntax:**
```bash
kill [OPTIONS] PID
```

**Common Signals:**

| Signal | Number | Description |
|--------|--------|-------------|
| `SIGTERM` | 15 | Graceful termination (default) |
| `SIGKILL` | 9 | Force kill — cannot be caught or ignored |
| `SIGHUP` | 1 | Hang up — often used to reload config |
| `SIGSTOP` | 19 | Pause the process |
| `SIGCONT` | 18 | Resume a paused process |

**Common Flags:**

| Flag | Description |
|------|-------------|
| `-9` | Send SIGKILL (force kill) |
| `-15` | Send SIGTERM (graceful, default) |
| `-l` | List all available signal names |

**Examples from your history:**
```bash
kill 2774           # Send SIGTERM to process 2774
kill -f 2774        # (Note: -f is not standard; use -9 for force kill)
```

**More examples:**
```bash
kill -9 2774                # Force kill process 2774
kill -SIGTERM 2774          # Gracefully terminate process 2774
killall nginx               # Kill all processes named 'nginx'
pkill -f "python script"    # Kill processes matching a pattern
```

> **Workflow:** Use `ps aux | grep PROCESS` or `htop` to find the PID, then `kill PID`.

---

## 👤 User Management

---

### 26. `useradd` — Add a New User

Creates a new user account on the system.

**Syntax:**
```bash
sudo useradd [OPTIONS] USERNAME
```

**Common Flags:**

| Flag | Description |
|------|-------------|
| `-m` | Create a home directory for the user (`/home/USERNAME`) |
| `-s SHELL` | Set the user's login shell (e.g., `/bin/bash`) |
| `-G GROUPS` | Add user to supplementary groups |
| `-d DIR` | Specify a custom home directory |
| `-c COMMENT` | Add a comment (usually full name) |
| `-e DATE` | Set account expiration date (YYYY-MM-DD) |
| `-u UID` | Specify a custom user ID |

**Examples from your history:**
```bash
sudo useradd daddy                      # Create user 'daddy' (no home dir)
sudo useradd -m daddy3                  # Create user 'daddy3' with home directory
sudo useradd -m kallu -s /bin/bash      # Create 'kallu' with home dir and bash shell
sudo useradd -m messi -s /bin/bash      # Create 'messi' with home dir and bash shell
```

> **Tip:** Always use `-m` to create a home directory and `-s /bin/bash` for an interactive shell.

**Verify user creation:**
```bash
cat /etc/passwd         # Lists all user accounts
```

---

### 27. `userdel` — Delete a User

Removes a user account from the system.

**Syntax:**
```bash
sudo userdel [OPTIONS] USERNAME
```

**Common Flags:**

| Flag | Description |
|------|-------------|
| `-r` | Remove the user's home directory and mail spool |
| `-f` | Force removal even if user is logged in |

**Examples from your history:**
```bash
sudo userdel daddy3         # Delete user 'daddy3' (keep home dir)
sudo userdel daddy          # Delete user 'daddy'
sudo userdel kallu          # Delete user 'kallu'
```

**More examples:**
```bash
sudo userdel -r olduser     # Delete user AND their home directory
sudo userdel -f staleuser   # Force delete a user
```

---

### 28. `passwd` — Change User Password

Sets or changes the password for a user account.

**Syntax:**
```bash
passwd [OPTIONS] [USERNAME]
```

**Common Flags:**

| Flag | Description |
|------|-------------|
| `-l` | Lock the user account |
| `-u` | Unlock the user account |
| `-d` | Delete the password (make account passwordless) |
| `-e` | Expire the password (force change on next login) |
| `-S` | Display password status |

**Examples from your history:**
```bash
sudo passwd daddy3      # Set password for 'daddy3'
sudo passwd kallu       # Set password for 'kallu'
sudo passwd messi       # Set password for 'messi'
```

**More examples:**
```bash
passwd                  # Change your own password
sudo passwd -l user1    # Lock user1's account
sudo passwd -u user1    # Unlock user1's account
sudo passwd -e user1    # Force user1 to change password at next login
```

---

### 29. `su` — Switch User

Switches to another user account within the same terminal session.

**Syntax:**
```bash
su [OPTIONS] [USERNAME]
```

**Common Flags:**

| Flag | Description |
|------|-------------|
| `-` or `-l` | Start a login shell (loads user's environment) |
| `-c COMMAND` | Run a single command as the target user, then return |
| `-s SHELL` | Use a specific shell |

**Examples from your history:**
```bash
su daddy3       # Switch to user 'daddy3'
su kallu        # Switch to user 'kallu'
su messi        # Switch to user 'messi'
```

**More examples:**
```bash
su -                    # Switch to root with a login shell
su - alice              # Switch to alice with full environment
su -c "ls /root" root   # Run a single command as root
exit                    # Return to original user
```

---

### 30. `usermod` — Modify a User Account

Modifies an existing user account's properties (groups, shell, home directory, etc.).

**Syntax:**
```bash
sudo usermod [OPTIONS] USERNAME
```

**Common Flags:**

| Flag | Description |
|------|-------------|
| `-aG GROUP` | **Append** user to a supplementary group |
| `-G GROUPS` | Set the user's supplementary groups (replaces existing) |
| `-s SHELL` | Change the user's login shell |
| `-d DIR` | Change the user's home directory |
| `-l NEW_NAME` | Change the username |
| `-L` | Lock the user account |
| `-U` | Unlock the user account |

**Examples from your history:**
```bash
sudo usermod -aG mygrp dkjdi    # Add user 'dkjdi' to group 'mygrp'
```

**More examples:**
```bash
sudo usermod -aG docker alice           # Add alice to docker group
sudo usermod -s /bin/zsh bob            # Change bob's shell to zsh
sudo usermod -d /newhome/alice alice    # Change alice's home directory
sudo usermod -l newname oldname         # Rename a user
```

> ⚠️ **Warning:** `-G` without `-a` **replaces** all supplementary groups! Always use `-aG` to **add** to existing groups.

---

## 👥 Group Management

---

### 31. `groupadd` — Create a New Group

Creates a new user group on the system.

**Syntax:**
```bash
sudo groupadd [OPTIONS] GROUP_NAME
```

**Common Flags:**

| Flag | Description |
|------|-------------|
| `-g GID` | Specify a custom group ID |
| `-f` | Exit successfully if the group already exists |

**Examples from your history:**
```bash
sudo groupadd mygrp     # Create a group called 'mygrp'
```

**More examples:**
```bash
sudo groupadd -g 1500 devteam      # Create group with specific GID
sudo groupadd -f existinggroup     # No error if group already exists
```

**Verify group creation:**
```bash
cat /etc/group          # List all groups
```

---

### 32. `gpasswd` — Manage Group Memberships

Administers group passwords and memberships. An alternative to `usermod -aG`.

**Syntax:**
```bash
sudo gpasswd [OPTIONS] GROUP
```

**Common Flags:**

| Flag | Description |
|------|-------------|
| `-a USER` | Add a user to the group |
| `-d USER` | Remove a user from the group |
| `-M USER1,USER2` | Set the list of group members (replaces all) |
| `-A USER` | Set a user as group administrator |
| `-r` | Remove the group password |

**Examples from your history:**
```bash
sudo gpasswd -M messi          # (Incomplete) Set group members
```

**More examples:**
```bash
sudo gpasswd -a alice devteam              # Add alice to devteam
sudo gpasswd -d bob devteam                # Remove bob from devteam
sudo gpasswd -M alice,bob,charlie devteam  # Set all members of devteam
```

---

### 33. `groups` — Show Group Memberships

Displays the groups a user belongs to.

**Syntax:**
```bash
groups [USERNAME...]
```

**Examples from your history:**
```bash
groups              # Show groups of the current user
groups dkjdi        # Show groups for user 'dkjdi'
groups messi        # Show groups for user 'messi'
groups dkjdi messi  # Show groups for multiple users
```

**Example output:**
```bash
$ groups dkjdi
dkjdi : dkjdi adm sudo mygrp
```

---

## 🆕 Essential Additional Commands

> These commands were not in your terminal history but are **essential** for every Linux / DevOps user.

---

### 34. `pwd` — Print Working Directory

Displays the full absolute path of the current directory you are in.

**Syntax:**
```bash
pwd [OPTIONS]
```

**Common Flags:**

| Flag | Description |
|------|-------------|
| `-L` | Print the logical path (follows symlinks, default) |
| `-P` | Print the physical path (resolves symlinks) |

**Examples:**
```bash
pwd
# Output: /home/dkjdi

cd /var/log
pwd
# Output: /var/log
```

> **Tip:** Use `pwd` whenever you're unsure which directory you're in. It's one of the most frequently used commands.

---

### 35. `find` — Search for Files

Searches for files and directories recursively based on name, type, size, permissions, date, and more.

**Syntax:**
```bash
find [PATH] [OPTIONS] [EXPRESSION]
```

**Common Flags:**

| Flag | Description |
|------|-------------|
| `-name "pattern"` | Search by filename (case-sensitive) |
| `-iname "pattern"` | Search by filename (case-insensitive) |
| `-type f` | Find only files |
| `-type d` | Find only directories |
| `-size +10M` | Find files larger than 10MB |
| `-size -1k` | Find files smaller than 1KB |
| `-mtime -7` | Modified within the last 7 days |
| `-mtime +30` | Modified more than 30 days ago |
| `-user USERNAME` | Find files owned by a specific user |
| `-perm 755` | Find files with specific permissions |
| `-exec CMD {} \;` | Execute a command on each result |
| `-delete` | Delete matching files |
| `-maxdepth N` | Limit search depth |
| `-empty` | Find empty files and directories |

**Examples:**
```bash
find . -name "*.txt"                        # Find all .txt files in current dir
find / -name "nginx.conf"                   # Find nginx.conf anywhere on system
find /home -type f -size +100M              # Find files larger than 100MB
find . -type f -mtime -7                    # Files modified in the last 7 days
find . -name "*.log" -delete                # Delete all .log files
find . -type f -name "*.sh" -exec chmod +x {} \;   # Make all .sh files executable
find /var/log -type f -empty                # Find empty log files
find . -maxdepth 2 -name "*.conf"           # Search only 2 levels deep
```

> **DevOps Use Case:** `find /var/log -name "*.log" -mtime +30 -delete` — clean up logs older than 30 days.

---

### 36. `grep` — Search Text Patterns

Searches for text patterns inside files. One of the most powerful and frequently used Linux commands.

**Syntax:**
```bash
grep [OPTIONS] "PATTERN" [FILE...]
```

**Common Flags:**

| Flag | Description |
|------|-------------|
| `-i` | Case-insensitive search |
| `-r` or `-R` | Recursive search through directories |
| `-n` | Show line numbers |
| `-c` | Count matching lines |
| `-l` | Show only filenames with matches |
| `-v` | Invert match — show lines that do NOT match |
| `-w` | Match whole words only |
| `-A N` | Show N lines AFTER each match |
| `-B N` | Show N lines BEFORE each match |
| `-C N` | Show N lines of context (before and after) |
| `-E` | Extended regex (same as `egrep`) |
| `--color` | Highlight matches in color |

**Examples:**
```bash
grep "error" /var/log/syslog                # Find "error" in syslog
grep -i "warning" /var/log/nginx/error.log  # Case-insensitive search
grep -r "TODO" /home/dkjdi/project/         # Search recursively in project
grep -n "root" /etc/passwd                  # Show line numbers
grep -c "GET" /var/log/nginx/access.log     # Count GET requests
grep -v "^#" /etc/nginx/nginx.conf          # Show lines that aren't comments
grep -rn "function" --include="*.js" .      # Search only .js files
```

**Combining with pipes:**
```bash
ps aux | grep nginx             # Find nginx processes
history | grep "apt install"    # Find past install commands
cat /etc/passwd | grep dkjdi    # Find your user entry
dmesg | grep -i "error"        # Search kernel messages for errors
```

> **DevOps Use Case:** `grep` combined with pipes (`|`) is the bread and butter of Linux troubleshooting.

---

### 37. `head` — View Beginning of File

Displays the first N lines of a file (default: 10 lines).

**Syntax:**
```bash
head [OPTIONS] [FILE]
```

**Common Flags:**

| Flag | Description |
|------|-------------|
| `-n N` | Show the first N lines |
| `-c N` | Show the first N bytes |
| `-q` | Quiet mode — suppress headers when multiple files |

**Examples:**
```bash
head /var/log/syslog                # Show first 10 lines
head -n 20 /etc/passwd              # Show first 20 lines
head -n 5 file1.txt file2.txt       # First 5 lines of each file
head -c 100 binary_file             # Show first 100 bytes
```

---

### 38. `tail` — View End of File

Displays the last N lines of a file (default: 10 lines). Critical for monitoring log files.

**Syntax:**
```bash
tail [OPTIONS] [FILE]
```

**Common Flags:**

| Flag | Description |
|------|-------------|
| `-n N` | Show the last N lines |
| `-f` | **Follow** — continuously display new lines as they are added (live monitoring) |
| `-F` | Like `-f`, but retries if the file is rotated/recreated |
| `-c N` | Show the last N bytes |

**Examples:**
```bash
tail /var/log/syslog                    # Show last 10 lines
tail -n 50 /var/log/nginx/error.log     # Show last 50 lines
tail -f /var/log/nginx/access.log       # LIVE monitor access logs (Ctrl+C to stop)
tail -F /var/log/syslog                 # Follow with retry on rotation
tail -n +5 file.txt                     # Show everything from line 5 onwards
```

> **DevOps Use Case:** `tail -f` is how you monitor log files in real time on a server. Essential for debugging.

---

### 39. `less` — Page Through File Contents

View file contents one screen at a time. Better than `cat` for large files.

**Syntax:**
```bash
less [OPTIONS] [FILE]
```

**Navigation inside `less`:**

| Key | Action |
|-----|--------|
| `Space` / `Page Down` | Next page |
| `b` / `Page Up` | Previous page |
| `g` | Go to beginning of file |
| `G` | Go to end of file |
| `/pattern` | Search forward |
| `?pattern` | Search backward |
| `n` | Next search result |
| `N` | Previous search result |
| `q` | Quit |
| `F` | Follow mode (like `tail -f`) |

**Examples:**
```bash
less /var/log/syslog                    # Browse a large log file
less +G /var/log/syslog                 # Open at the end of file
cat /etc/passwd | less                  # Pipe output into less
ps aux | less                           # Browse process list page by page
```

> **Tip:** `less` is "more than `more`" — it loads files faster and allows backward navigation.

---

### 40. `wc` — Word, Line, Character Count

Counts lines, words, and characters in a file.

**Syntax:**
```bash
wc [OPTIONS] [FILE...]
```

**Common Flags:**

| Flag | Description |
|------|-------------|
| `-l` | Count lines only |
| `-w` | Count words only |
| `-c` | Count bytes (characters) only |
| `-m` | Count characters (multi-byte aware) |

**Examples:**
```bash
wc /etc/passwd                          # Show lines, words, and bytes
wc -l /etc/passwd                       # Count number of user accounts
wc -l /var/log/nginx/access.log         # Count total HTTP requests
ls | wc -l                              # Count files in current directory
cat file.txt | wc -w                    # Count words in file
```

**Example output:**
```bash
$ wc /etc/passwd
  42   67  2436 /etc/passwd
#  lines words bytes filename
```

---

### 41. `sort` — Sort Lines of Text

Sorts lines in a file or piped input.

**Syntax:**
```bash
sort [OPTIONS] [FILE]
```

**Common Flags:**

| Flag | Description |
|------|-------------|
| `-r` | Reverse order (descending) |
| `-n` | Numeric sort (instead of alphabetical) |
| `-k N` | Sort by Nth column |
| `-u` | Remove duplicates while sorting |
| `-t CHAR` | Use CHAR as field delimiter |
| `-h` | Human-readable numeric sort (1K, 2M, 3G) |
| `-f` | Case-insensitive sort |

**Examples:**
```bash
sort names.txt                          # Sort file alphabetically
sort -r numbers.txt                     # Sort in reverse order
sort -n scores.txt                      # Sort numerically
sort -u duplicates.txt                  # Sort and remove duplicates
du -sh * | sort -hr                     # Sort disk usage by size (largest first)
ps aux --sort=-%mem | head              # Top memory-consuming processes
```

---

### 42. `uniq` — Filter Duplicate Lines

Removes or reports **adjacent** duplicate lines. Usually used after `sort`.

**Syntax:**
```bash
uniq [OPTIONS] [INPUT [OUTPUT]]
```

**Common Flags:**

| Flag | Description |
|------|-------------|
| `-c` | Prefix lines with the count of occurrences |
| `-d` | Only print duplicated lines |
| `-u` | Only print unique lines |
| `-i` | Case-insensitive comparison |

**Examples:**
```bash
sort access.log | uniq                  # Remove duplicates
sort access.log | uniq -c               # Count occurrences
sort ips.txt | uniq -c | sort -rn       # Top most frequent IPs
sort names.txt | uniq -d                # Show only duplicates
```

> **DevOps Use Case:** `awk '{print $1}' access.log | sort | uniq -c | sort -rn | head` — find top 10 IPs hitting your server.

---

### 43. `top` — System Process Monitor

Real-time system monitor showing processes, CPU, and memory usage. `htop` is the improved version.

**Syntax:**
```bash
top [OPTIONS]
```

**Key Bindings inside `top`:**

| Key | Action |
|-----|--------|
| `q` | Quit |
| `M` | Sort by memory usage |
| `P` | Sort by CPU usage |
| `k` | Kill a process (enter PID) |
| `1` | Show individual CPU cores |
| `c` | Toggle full command line display |
| `r` | Renice (change priority) of a process |

**Common Flags:**

| Flag | Description |
|------|-------------|
| `-d N` | Refresh every N seconds |
| `-u USER` | Show only processes for a user |
| `-p PID` | Monitor a specific process |
| `-n N` | Exit after N refreshes |
| `-b` | Batch mode (useful for scripting) |

**Examples:**
```bash
top                                 # Launch interactive monitor
top -d 2                            # Refresh every 2 seconds
top -u dkjdi                        # Show only your processes
top -bn1 | head -20                 # One-shot snapshot (for scripts)
```

---

### 44. `df` — Disk Free Space

Shows disk space usage for mounted file systems.

**Syntax:**
```bash
df [OPTIONS] [PATH]
```

**Common Flags:**

| Flag | Description |
|------|-------------|
| `-h` | Human-readable sizes (KB, MB, GB) |
| `-T` | Show filesystem type |
| `-i` | Show inode usage instead of block usage |
| `-a` | Include pseudo and duplicate filesystems |

**Examples:**
```bash
df -h                               # Show all disk usage (human-readable)
df -hT                              # Include filesystem type
df -h /                             # Show usage for root partition
df -i                               # Check inode usage
```

**Example output:**
```
Filesystem      Size  Used Avail Use% Mounted on
/dev/sda1        50G   25G   23G  53% /
tmpfs           3.9G     0  3.9G   0% /dev/shm
```

> **DevOps Use Case:** Set up alerts when `Use%` exceeds 80% to prevent disk full issues.

---

### 45. `du` — Disk Usage

Shows disk space used by files and directories.

**Syntax:**
```bash
du [OPTIONS] [PATH]
```

**Common Flags:**

| Flag | Description |
|------|-------------|
| `-h` | Human-readable sizes |
| `-s` | Summary — show only total for each argument |
| `-a` | Show sizes for files (not just directories) |
| `--max-depth=N` | Limit depth of directory listing |
| `-c` | Show grand total |

**Examples:**
```bash
du -sh /var/log/                    # Total size of /var/log
du -sh *                            # Size of each item in current dir
du -h --max-depth=1 /home/          # One level deep inside /home
du -sh * | sort -hr | head -10      # Top 10 largest items
du -ah /var/log | sort -rh | head   # Largest files in /var/log
```

> **DevOps Use Case:** `du -sh * | sort -hr | head` — quickly find what's eating disk space.

---

### 46. `free` — Memory Usage

Displays total, used, and available RAM and swap memory.

**Syntax:**
```bash
free [OPTIONS]
```

**Common Flags:**

| Flag | Description |
|------|-------------|
| `-h` | Human-readable (MB, GB) |
| `-m` | Display in megabytes |
| `-g` | Display in gigabytes |
| `-s N` | Continuously refresh every N seconds |
| `-t` | Show total row |

**Examples:**
```bash
free -h                             # Human-readable memory info
free -m                             # Memory in megabytes
free -h -s 5                        # Refresh every 5 seconds
```

**Example output:**
```
              total        used        free      shared  buff/cache   available
Mem:          7.8Gi       3.2Gi       1.5Gi       256Mi       3.1Gi       4.1Gi
Swap:         2.0Gi       512Mi       1.5Gi
```

> **Key concept:** `available` is more important than `free` — it includes reclaimable buffer/cache memory.

---

### 47. `uname` — System Information

Prints system information about the OS and kernel.

**Syntax:**
```bash
uname [OPTIONS]
```

**Common Flags:**

| Flag | Description |
|------|-------------|
| `-a` | All information |
| `-s` | Kernel name |
| `-r` | Kernel release (version) |
| `-m` | Machine hardware architecture (x86_64, arm, etc.) |
| `-n` | Network hostname |
| `-o` | Operating system name |

**Examples:**
```bash
uname -a                # Show all system info
uname -r                # Show kernel version
uname -m                # Show architecture (e.g., x86_64)
uname -o                # Show OS (e.g., GNU/Linux)
```

**Example output:**
```
$ uname -a
Linux DESKTOP-5ELTJLT 5.15.0-76-generic #83-Ubuntu SMP x86_64 GNU/Linux
```

---

### 48. `hostname` — System Hostname

Displays or sets the system's hostname.

**Syntax:**
```bash
hostname [OPTIONS]
```

**Common Flags:**

| Flag | Description |
|------|-------------|
| `-I` | Show all IP addresses of the host |
| `-f` | Show fully qualified domain name (FQDN) |
| `-s` | Show short hostname |

**Examples:**
```bash
hostname                # Show hostname
hostname -I             # Show IP addresses
hostname -f             # Show FQDN
sudo hostname newname   # Temporarily change hostname
```

---

### 49. `uptime` — System Uptime

Shows how long the system has been running, plus load averages.

**Syntax:**
```bash
uptime [OPTIONS]
```

**Common Flags:**

| Flag | Description |
|------|-------------|
| `-p` | Pretty format (e.g., "up 3 days, 2 hours") |
| `-s` | Show since when the system has been running |

**Examples:**
```bash
uptime                  # Show uptime + load average
uptime -p               # Human-readable uptime
uptime -s               # Show start date/time
```

**Example output:**
```
$ uptime
 10:30:15 up 3 days, 2:15, 2 users, load average: 0.15, 0.20, 0.18
```

> **Load averages** are for 1, 5, and 15 minutes. If consistently > number of CPU cores, the system is overloaded.

---

### 50. `id` — User Identity Info

Shows the UID, GID, and group memberships of a user.

**Syntax:**
```bash
id [OPTIONS] [USERNAME]
```

**Common Flags:**

| Flag | Description |
|------|-------------|
| `-u` | Print only the effective user ID |
| `-g` | Print only the effective group ID |
| `-G` | Print all group IDs |
| `-n` | Print names instead of numbers (use with -u, -g, -G) |

**Examples:**
```bash
id                      # Show current user's full identity
id dkjdi                # Show identity of user 'dkjdi'
id -u                   # Show numeric UID
id -Gn dkjdi            # Show all group names for dkjdi
```

**Example output:**
```
$ id dkjdi
uid=1000(dkjdi) gid=1000(dkjdi) groups=1000(dkjdi),4(adm),27(sudo),1001(mygrp)
```

---

### 51. `which` — Locate a Command

Shows the full path of a command's executable.

**Syntax:**
```bash
which [COMMAND]
```

**Related commands:**

| Command | Description |
|---------|-------------|
| `which` | Shows the path of the command |
| `whereis` | Shows binary, source, and man page locations |
| `type` | Shows whether it's a builtin, alias, or file |

**Examples:**
```bash
which ls                # Output: /usr/bin/ls
which python3           # Output: /usr/bin/python3
which nginx             # Check if nginx is installed
whereis nginx           # Show binary + man page locations
type cd                 # Output: cd is a shell builtin
```

---

## 🌐 Networking

---

### 52. `wget` — Download Files from Web

Downloads files from the internet via HTTP, HTTPS, and FTP.

**Syntax:**
```bash
wget [OPTIONS] URL
```

**Common Flags:**

| Flag | Description |
|------|-------------|
| `-O FILE` | Save with a custom filename |
| `-P DIR` | Save to a specific directory |
| `-q` | Quiet mode (no output) |
| `-c` | Continue a partially downloaded file |
| `-r` | Recursive download (download entire site) |
| `--limit-rate=200k` | Limit download speed |
| `-b` | Download in background |
| `--no-check-certificate` | Skip SSL verification |

**Examples:**
```bash
wget https://example.com/file.tar.gz                    # Download a file
wget -O custom_name.zip https://example.com/file.zip    # Save with custom name
wget -P /tmp/ https://example.com/file.tar.gz           # Save to /tmp
wget -c https://example.com/large_file.iso              # Resume download
wget -q https://example.com/script.sh                   # Quiet download
```

> **Install:** `sudo apt install wget`

---

### 53. `curl` — Transfer Data from URLs

Transfers data to or from a server. More versatile than `wget` — supports APIs, POST requests, headers, and more.

**Syntax:**
```bash
curl [OPTIONS] URL
```

**Common Flags:**

| Flag | Description |
|------|-------------|
| `-o FILE` | Save output to a file |
| `-O` | Save with original filename |
| `-L` | Follow redirects |
| `-I` | Show only response headers |
| `-s` | Silent mode (no progress bar) |
| `-X METHOD` | Specify HTTP method (GET, POST, PUT, DELETE) |
| `-H "Header"` | Add a custom header |
| `-d "data"` | Send POST data |
| `-u user:pass` | HTTP authentication |
| `-k` | Skip SSL verification |

**Examples:**
```bash
curl https://example.com                                # Fetch a webpage
curl -o page.html https://example.com                   # Save to file
curl -O https://example.com/file.tar.gz                 # Save with original name
curl -I https://example.com                             # View response headers only
curl -L https://short.url/abc                           # Follow redirects
curl -s https://api.github.com/users/dkjdi              # Silent API call
curl -X POST -d '{"key":"value"}' -H "Content-Type: application/json" https://api.example.com/data
```

> **DevOps Use Case:** `curl` is the go-to tool for testing APIs, health checks, and web services from the command line.

---

### 54. `ping` — Test Network Connectivity

Sends ICMP packets to a host to check if it's reachable and measure latency.

**Syntax:**
```bash
ping [OPTIONS] HOST
```

**Common Flags:**

| Flag | Description |
|------|-------------|
| `-c N` | Send only N pings and stop |
| `-i N` | Wait N seconds between pings |
| `-W N` | Timeout in seconds for each reply |
| `-s SIZE` | Packet size in bytes |
| `-q` | Quiet — only show summary |

**Examples:**
```bash
ping google.com                     # Continuous ping (Ctrl+C to stop)
ping -c 5 google.com                # Send exactly 5 pings
ping -c 3 192.168.1.1               # Ping local router
ping -c 4 -W 2 10.0.0.1            # Ping with 2-second timeout
```

**Example output:**
```
PING google.com (142.250.190.78) 56(84) bytes of data.
64 bytes from 142.250.190.78: icmp_seq=1 ttl=117 time=12.3 ms
64 bytes from 142.250.190.78: icmp_seq=2 ttl=117 time=11.8 ms
--- google.com ping statistics ---
2 packets transmitted, 2 received, 0% packet loss, time 1001ms
rtt min/avg/max/mdev = 11.8/12.0/12.3/0.25 ms
```

---

### 55. `ssh` — Secure Shell (Remote Login)

Securely connects to a remote server over an encrypted connection.

**Syntax:**
```bash
ssh [OPTIONS] [USER@]HOST
```

**Common Flags:**

| Flag | Description |
|------|-------------|
| `-p PORT` | Connect to a non-default port |
| `-i FILE` | Use a specific private key file |
| `-v` | Verbose mode (for debugging) |
| `-L local:host:remote` | Local port forwarding (tunnel) |
| `-N` | No command — just forward ports |
| `-o OPTION` | Pass config options |

**Examples:**
```bash
ssh user@192.168.1.100                              # Connect to remote server
ssh -p 2222 user@server.com                         # Connect on port 2222
ssh -i ~/.ssh/mykey.pem ec2-user@aws-instance       # Use specific SSH key
ssh user@server "ls /var/log"                       # Run command remotely
ssh -L 8080:localhost:80 user@server                # Port forward: local 8080 → remote 80
```

**SSH Key Setup:**
```bash
ssh-keygen -t rsa -b 4096              # Generate SSH key pair
ssh-copy-id user@server                 # Copy public key to remote server
# Now you can login without a password!
```

> **DevOps Use Case:** SSH is the primary way to manage remote servers. Learn key-based authentication early.

---

### 56. `scp` — Secure Copy Over SSH

Copies files between local and remote machines over SSH.

**Syntax:**
```bash
scp [OPTIONS] SOURCE DESTINATION
```

**Common Flags:**

| Flag | Description |
|------|-------------|
| `-r` | Copy directories recursively |
| `-P PORT` | Use a non-default SSH port |
| `-i FILE` | Use a specific SSH key |
| `-C` | Enable compression during transfer |
| `-v` | Verbose mode |

**Examples:**
```bash
# Copy local file to remote server
scp file.txt user@server:/home/user/

# Copy from remote server to local
scp user@server:/var/log/syslog ./

# Copy entire directory recursively
scp -r project/ user@server:/home/user/project/

# Use specific port
scp -P 2222 file.txt user@server:/tmp/

# Copy between two remote servers
scp user1@server1:/file.txt user2@server2:/file.txt
```

---

## 📦 Compression & Archiving

---

### 57. `tar` — Archive Files

Creates, extracts, and manages archive files (`.tar`, `.tar.gz`, `.tar.bz2`).

**Syntax:**
```bash
tar [OPTIONS] [ARCHIVE_FILE] [FILES...]
```

**Essential Flag Combos:**

| Flags | Description |
|-------|-------------|
| `-czf` | **Create** a gzip-compressed archive |
| `-xzf` | **Extract** a gzip-compressed archive |
| `-cjf` | Create a bzip2-compressed archive |
| `-xjf` | Extract a bzip2-compressed archive |
| `-cf` | Create an uncompressed archive |
| `-xf` | Extract an uncompressed archive |
| `-tf` | **List** contents of an archive (without extracting) |

**Individual Flags:**

| Flag | Description |
|------|-------------|
| `-c` | Create a new archive |
| `-x` | Extract from archive |
| `-f FILE` | Specify archive filename |
| `-z` | Use gzip compression |
| `-j` | Use bzip2 compression |
| `-v` | Verbose — list files being processed |
| `-t` | List contents of archive |
| `-C DIR` | Extract to a specific directory |

**Examples:**
```bash
# Create a compressed archive
tar -czf backup.tar.gz /home/dkjdi/project/

# Extract an archive
tar -xzf backup.tar.gz

# Extract to a specific directory
tar -xzf backup.tar.gz -C /tmp/

# List contents without extracting
tar -tf backup.tar.gz

# Create archive with verbose output
tar -czvf archive.tar.gz file1.txt file2.txt dir/

# Extract a .tar.bz2 archive
tar -xjf archive.tar.bz2
```

> **Memory aid:** **C**reate, e**X**tract, **F**ile, **Z**ip (gzip) → `czf` and `xzf`

---

### 58. `ln` — Create Links

Creates hard links or symbolic (soft) links to files.

**Syntax:**
```bash
ln [OPTIONS] TARGET LINK_NAME
```

**Types of Links:**

| Type | Description |
|------|-------------|
| **Hard link** | Another name for the same file (shares inode). Cannot link directories or cross filesystems. |
| **Symbolic link** (`-s`) | A pointer/shortcut to another file. Can link directories and cross filesystems. |

**Common Flags:**

| Flag | Description |
|------|-------------|
| `-s` | Create a symbolic (soft) link |
| `-f` | Force — overwrite existing link |
| `-v` | Verbose — print each link created |

**Examples:**
```bash
ln -s /var/log/nginx/access.log ~/nginx_log     # Create a symbolic link
ln -s /usr/bin/python3 /usr/bin/python           # Create a python alias
ln file.txt hardlink.txt                          # Create a hard link
ln -sf /new/target existing_link                  # Force update an existing link
ls -l ~/nginx_log                                 # Verify: shows -> /var/log/...
```

> **DevOps Use Case:** Symbolic links are used everywhere — config file management, version switching, shared resources.

---

## 🐚 Shell Configuration & Environment

---

### 59. `alias` — Create Command Shortcuts

Creates a shortcut name for a longer command.

**Syntax:**
```bash
alias NAME='COMMAND'
```

**Examples:**
```bash
alias ll='ls -la'                           # Quick detailed listing
alias update='sudo apt update && sudo apt upgrade -y'
alias gs='git status'
alias ..='cd ..'
alias ...='cd ../..'
alias ports='sudo netstat -tulnp'           # Show listening ports
alias myip='curl ifconfig.me'              # Show public IP

# Remove an alias
unalias ll

# List all aliases
alias
```

**Make aliases permanent** — add them to `~/.bashrc` or `~/.bash_aliases`:
```bash
echo "alias ll='ls -la'" >> ~/.bashrc
source ~/.bashrc        # Reload to apply
```

---

### 60. `export` — Set Environment Variables

Sets environment variables that are available to child processes.

**Syntax:**
```bash
export VARIABLE_NAME=VALUE
```

**Examples:**
```bash
export PATH=$PATH:/opt/myapp/bin            # Add to PATH
export EDITOR=vim                            # Set default editor
export NODE_ENV=production                   # Set Node.js environment
export MY_VAR="Hello World"                  # Set a custom variable

echo $PATH                                   # View a variable
echo $HOME                                   # View home directory
env                                           # List all environment variables
printenv                                      # Same as env
unset MY_VAR                                  # Remove a variable
```

**Make permanent** — add to `~/.bashrc` or `~/.profile`:
```bash
echo 'export PATH=$PATH:/opt/myapp/bin' >> ~/.bashrc
source ~/.bashrc
```

> **Important system variables:** `$HOME`, `$USER`, `$PATH`, `$SHELL`, `$PWD`, `$EDITOR`

---

## ⏰ Automation & Scheduling

---

### 61. `crontab` — Schedule Tasks

Creates scheduled tasks (cron jobs) that run automatically at specified times.

**Syntax:**
```bash
crontab [OPTIONS]
```

**Common Flags:**

| Flag | Description |
|------|-------------|
| `-e` | Edit your crontab file |
| `-l` | List your cron jobs |
| `-r` | Remove all cron jobs |
| `-u USER` | Manage another user's crontab (requires sudo) |

**Cron Expression Format:**
```
┌───────── minute (0 - 59)
│ ┌───────── hour (0 - 23)
│ │ ┌───────── day of month (1 - 31)
│ │ │ ┌───────── month (1 - 12)
│ │ │ │ ┌───────── day of week (0 - 6) (Sunday = 0)
│ │ │ │ │
* * * * * command_to_run
```

**Common Patterns:**

| Expression | Meaning |
|-----------|---------|
| `* * * * *` | Every minute |
| `0 * * * *` | Every hour (at minute 0) |
| `0 0 * * *` | Every day at midnight |
| `0 0 * * 0` | Every Sunday at midnight |
| `0 6 * * 1-5` | Weekdays at 6:00 AM |
| `*/5 * * * *` | Every 5 minutes |
| `0 0 1 * *` | First day of every month |
| `@reboot` | Once at startup |

**Examples:**
```bash
crontab -e                                      # Edit cron jobs
crontab -l                                      # List all cron jobs

# Example cron entries (add these via `crontab -e`):
0 2 * * * /home/dkjdi/backup.sh                 # Daily backup at 2 AM
*/10 * * * * /usr/bin/health_check.sh            # Health check every 10 min
0 0 * * 0 sudo apt update && sudo apt upgrade -y  # Weekly update on Sunday
@reboot /home/dkjdi/startup_script.sh            # Run on boot
```

> **DevOps Use Case:** Cron is essential for log rotation, backups, monitoring scripts, and system maintenance.

---

## 📋 System Logs & Services (Additional)

---

### 62. `journalctl` — View System Logs

Queries the systemd journal for logs. The modern replacement for `/var/log/syslog`.

**Syntax:**
```bash
journalctl [OPTIONS]
```

**Common Flags:**

| Flag | Description |
|------|-------------|
| `-u SERVICE` | Show logs for a specific service |
| `-f` | Follow logs in real time (like `tail -f`) |
| `-n N` | Show last N lines |
| `-p PRIORITY` | Filter by priority (emerg, alert, crit, err, warning, notice, info, debug) |
| `--since "TIME"` | Show logs since a specific time |
| `--until "TIME"` | Show logs until a specific time |
| `-b` | Show logs since last boot |
| `--no-pager` | Print all output (don't use pager) |
| `-xe` | Jump to end + show extra info |

**Examples:**
```bash
journalctl                                          # All logs
journalctl -u nginx                                 # Nginx service logs
journalctl -u nginx -f                              # Follow nginx logs live
journalctl -u nginx --since "1 hour ago"            # Last hour of nginx logs
journalctl -p err                                   # Only errors
journalctl -b                                       # Logs since last boot
journalctl --since "2026-06-15" --until "2026-06-16"   # Date range
journalctl -u nginx -n 50 --no-pager                # Last 50 lines, no pager
journalctl --disk-usage                             # Check log storage size
```

> **DevOps Use Case:** `journalctl -u SERVICE -f` is how you debug failing services on modern Linux systems.

---

## ⚡ System Power Management

---

### 63. `shutdown` / `reboot` — Power Management

Shut down or restart the system.

**Syntax:**
```bash
sudo shutdown [OPTIONS] [TIME] [MESSAGE]
sudo reboot [OPTIONS]
```

**`shutdown` Flags:**

| Flag | Description |
|------|-------------|
| `-h now` | Halt (shut down) immediately |
| `-r now` | Reboot immediately |
| `-h +N` | Shut down in N minutes |
| `-c` | Cancel a pending shutdown |
| `-P` | Power off |

**Examples:**
```bash
sudo shutdown -h now                    # Shut down immediately
sudo shutdown -r now                    # Reboot immediately
sudo shutdown -h +30 "Maintenance"      # Shut down in 30 min with message
sudo shutdown -c                        # Cancel a pending shutdown
sudo reboot                             # Reboot (shorthand)
sudo poweroff                           # Power off (shorthand)
```

> ⚠️ **Warning:** Always save your work before running `shutdown` or `reboot`!

---

## 🔗 Pipe & Redirection — Shell Operators

---

### 64. `Pipe & Redirection` — Operators

These are not commands but **operators** that connect commands together. Essential for Linux proficiency.

**Pipe (`|`):**

Sends the output of one command as input to another.

```bash
command1 | command2 | command3
```

**Examples:**
```bash
ls -la | less                           # Browse long directory listing
ps aux | grep nginx                     # Find nginx processes
cat /etc/passwd | wc -l                 # Count user accounts
history | grep "apt" | tail -5          # Last 5 apt commands
cat access.log | sort | uniq -c | sort -rn | head -10   # Top 10 IPs
```

**Output Redirection:**

| Operator | Description |
|----------|-------------|
| `>` | Write stdout to file (overwrites) |
| `>>` | Append stdout to file |
| `2>` | Write stderr (errors) to file |
| `2>>` | Append stderr to file |
| `&>` | Write both stdout and stderr to file |
| `2>&1` | Redirect stderr to stdout |
| `/dev/null` | Discard output (black hole) |

**Examples:**
```bash
echo "Hello" > file.txt                 # Write to file (overwrite)
echo "World" >> file.txt                # Append to file
ls /nonexistent 2> error.log            # Redirect errors to file
command > output.log 2>&1               # Both output and errors to same file
command > /dev/null 2>&1                # Discard ALL output (silent)
```

**Input Redirection:**

| Operator | Description |
|----------|-------------|
| `<` | Read input from file |
| `<<EOF` | Here document — inline input block |

**Examples:**
```bash
sort < unsorted.txt                     # Sort file via input redirect
wc -l < /etc/passwd                     # Count lines via input redirect

cat <<EOF > config.txt                  # Create file with here document
server_name=myserver
port=8080
EOF
```

**Command Chaining:**

| Operator | Description |
|----------|-------------|
| `;` | Run commands sequentially (regardless of success) |
| `&&` | Run next command only if the previous **succeeded** |
| `\|\|` | Run next command only if the previous **failed** |

**Examples:**
```bash
mkdir project && cd project             # cd only if mkdir succeeds
apt update && apt upgrade               # upgrade only if update succeeds
ping -c1 server || echo "Server down"   # alert if ping fails
command1 ; command2 ; command3          # run all regardless
```

---

## 📂 Important System Files Referenced

These system files appeared in your command history:

| File | Description |
|------|-------------|
| `/etc/passwd` | User account information (username, UID, shell, home dir) |
| `/etc/group` | Group definitions and memberships |
| `/etc/shadow` | Encrypted user passwords (root only) |
| `/etc/sudoers` | Sudo permission configuration |
| `/etc/hostname` | System hostname |
| `/etc/hosts` | Local DNS mappings |
| `/etc/ssh/sshd_config` | SSH server configuration |
| `/etc/crontab` | System-wide cron schedule |
| `/var/log/syslog` | General system log |
| `/var/log/auth.log` | Authentication/login log |
| `/var/log/nginx/access.log` | Nginx HTTP access log |
| `/var/log/nginx/error.log` | Nginx error log |
| `/var/www/html/index.html` | Default Nginx web page |
| `~/.bashrc` | User's bash shell configuration |
| `~/.bash_history` | User's command history |
| `~/.ssh/` | SSH keys and configuration directory |

---

## 🧭 Quick Reference Cheat Sheet

### File Operations
```bash
pwd                     # Print current directory
ls -la                  # List all files with details
cd /path/to/dir         # Change directory
cat file.txt            # View file contents
less file.txt           # Page through large file
head -n 20 file.txt     # First 20 lines
tail -f /var/log/syslog # Live-follow a log file
touch newfile.txt       # Create empty file
cp src dst              # Copy file
mv src dst              # Move/rename file
rm file.txt             # Delete file
mkdir dirname           # Create directory
rmdir dirname           # Remove empty directory
ln -s target link       # Create symbolic link
```

### Searching & Text Processing
```bash
find . -name "*.txt"                    # Find files by name
grep -rn "pattern" /path/              # Search text recursively
grep -i "error" logfile | wc -l        # Count error occurrences
sort file.txt | uniq -c | sort -rn     # Frequency count
wc -l file.txt                          # Count lines
```

### User & Permission Management
```bash
sudo useradd -m -s /bin/bash newuser    # Create user with home + bash
sudo passwd newuser                      # Set user password
sudo userdel -r olduser                  # Delete user + home directory
sudo usermod -aG groupname username      # Add user to group
sudo groupadd newgroup                   # Create new group
chmod 755 file                           # Set permissions (rwxr-xr-x)
sudo chown user:group file               # Change ownership
id                                       # Show user identity
groups                                   # Show group memberships
```

### Package & Service Management
```bash
sudo apt update && sudo apt upgrade      # Update system
sudo apt install package_name            # Install package
systemctl status service_name            # Check service status
systemctl restart service_name           # Restart service
journalctl -u service_name -f           # Follow service logs
```

### Process Management
```bash
ps aux                  # List all processes
htop                    # Interactive process viewer
top                     # System monitor
kill -9 PID             # Force kill a process
free -h                 # Memory usage
df -h                   # Disk space
du -sh *                # Directory sizes
uptime                  # System uptime
```

### Networking
```bash
ping -c 4 google.com            # Test connectivity
curl -I https://example.com     # Check HTTP headers
wget https://example.com/file   # Download file
ssh user@server                 # Remote login
scp file.txt user@server:/path/ # Secure copy to remote
```

### Compression & Archiving
```bash
tar -czf archive.tar.gz dir/    # Create compressed archive
tar -xzf archive.tar.gz         # Extract archive
tar -tf archive.tar.gz          # List archive contents
```

### Shell & Automation
```bash
alias ll='ls -la'               # Create shortcut
export VAR=value                 # Set environment variable
crontab -e                      # Edit scheduled tasks
history | grep "keyword"        # Search command history
command1 | command2             # Pipe output
command > file.txt 2>&1         # Redirect all output to file
```

---

> 📝 **Note:** This reference covers **64 commands and operators** — 33 from your terminal history in `LINUX.md`, plus 31 essential additional commands every DevOps engineer should know. Each includes flags and examples for a complete learning resource.
