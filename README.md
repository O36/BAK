# BAK
A simple command-line utility for creating dated backup copies of files.

## What it does
bak creates a backup copy of a file with a timestamp to create clean backup filenames.
```bash
$ ls
file.txt

$ bak file.txt
Backup created: filetxt-2025-12-22.bak

$ ls
file.txt
filetxt-2025-12-22.bak
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
Backup created: configyaml-2025-12-22.bak

$ bak my.important.document.pdf
Backup created: my.importantdocumentpdf-2025-12-22.bak

$ bak script.sh
Backup created: scriptsh-2025-12-22.bak
```

## How it works
The script:
1. Takes a filename as input
2. Removes the dot before the file extension
3. Appends the current date in YYYY-MM-DD format
4. Adds a .bak extension
5. Creates a copy of the original file with the new name

## Requirements
* Bash shell
* Standard Unix utilities (cp, date, sed)

## License
* MIT
