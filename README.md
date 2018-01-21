# Ixesha

Make incremental snapshots to backup any folder to any location/server. 💪

Written in python. 🐍

###### Example

```bash
python3 ixesha.py --backup ~/ --output /mnt/backup/home
```

## Setup 

### Requirements 💾
- `Python3`
- `rsync` (min. v3.1.1)

### Installation

###### macOS

1. Install brew: `/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"`
2. Install `python3` and `rsync`: `brew install python3 rsync`

###### debian / ubuntu

1. `apt install -y python3 rsync`

###### windows

Well... I don't know 😅


## Usage 🚀

### Run 👾

```bash
python3 ixesha.py [-h|--help] -b|--backup <my-folder> -o|--output <where-to-save-it>
# or
./ixesha -b <my-folder> -o <where-to-save-it>
```

###### Example

Backup my home folder for example to some mounted drive
```bash
python3 ixesha.py --backup ~/ --output /mnt/backupdrive/home
```


### Arguments

- `-h` `--help` Show help dialog
- `-b` `--backup` The folder to be backed up
- `-o` `--output` Location where the snapshots will be saved


### Cron

If you want to run it every x... you can create a cronjob

###### Example:
Run the script every 5 Min (More details on [cronjobs](http://www.cyberciti.biz/faq/how-do-i-add-jobs-to-cron-under-linux-or-unix-oses/))

1. Edit your cron file with: `crontab -e`
2. Add: `*/5 * * * * python3 /path/to/ixesha.py -b /some/folder -o /some/backup/location`
