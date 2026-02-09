# BAK
A simple command-line utility for creating dated backup copies of files.

## What it does
bak creates a backup copy of a file with a timestamp to create clean backup filenames.
```bash
$ ls
file.txt

$ bak file.txt
Backup created: file.txt-2025-12-22.bak

$ ls
file.txt
file.txt-2025-12-22.bak
```

## Installation
Clone this repository:
```bash
git clone https://github.com/O36/BAK.git
cd BAK
```

Make the script executable:
```bash
chmod +x bak
```

Move it to a directory in your PATH:
```bash
# System-wide installation (requires sudo)
sudo mv bak /usr/local/bin/

# OR user-only installation
mkdir -p ~/bin
mv bak ~/bin/
# Make sure ~/bin is in your PATH
```

## Usage
```bash
bak [filename]
```

## Examples
```bash
$ bak config.yaml
Backup created: config.yaml-2025-12-22.bak

$ bak my.important.document.pdf
Backup created: my.important.document.pdf-2025-12-22.bak

# Full pathnames are also accepted, the backup will be placed in the same directory as the original
$ bak /var/log/script.sh
Backup created: /var/log/script.sh-2025-12-22.bak
```

## How it works
The script:
1. Takes a filename as input
2. Appends the current date in YYYY-MM-DD format
3. Adds a .bak extension
4. Creates a copy of the original file with the new name
5. If a backup of a file has already been made that day it will add \_(number) to new files

## Requirements
* Bash shell
* Standard Unix utilities (cp, date, sed)

## License
* MIT
