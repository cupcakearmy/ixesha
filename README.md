# Ixesha

🗄 Make incremental snapshots to backup any folder to any location/server.

🐍 Written in python.

## Quickstart 💥

```bash
git clone https://github.com/CupCakeArmy/ixesha
python3 ixesha/ixesha --install
rm -rf ixesha

ixesha --backup ~/ --output /mnt/backup/home
```

Whenever you want to do an incremental backup simply rerun the same command:

```bash
ixesha --backup ~/ --output /mnt/backup/home
```

###### How does it work? 🧐

All the snapshots are timestamped and you can delete all the old ones if you like (yes, really 💪), keeping only the last one. The backups are incremental, so they only save the changes you made and are therefore very space efficient. The latest backup is always the `./current` link to the last backup inside of the backup directory.

## Setup

### Requirements

- `Python3`
- `rsync` (min. v3.1.1)

##### macOS

1. Install [Brew](https://brew.sh/) if not already
2. Run: `brew install python3 rsync`

##### debian / ubuntu

Run: `apt install -y python3 rsync`

##### windows

Well... I don't know...

## Installation 🚂

__Optionally__ you can install/uninstall the script globally. Usefull but __not__ required.

It will be saved to: `/usr/local/bin/`

###### Install

```bash
python3 ixesha --install
```

###### Uninstall

```bash
python3 ixesha --uninstall
```

## Usage 👾

### Run 🚀

Run with: `python3 ixesha` or `./ixesha`

If [installed](#install) simply: `ixesha`

```bash
ixesha --backup <my-folder> --output <where-to-save-it>
```

###### Example

Backup my home folder for example to some mounted drive

```bash
ixesha --backup ~/ --output /mnt/backupdrive/home
```

### Arguments

- `-h` `--help` Show help dialog
- `-b` `--from` `--backup` The folder to be backed up
- `-o` `--to` `--output` Location where the snapshots will be saved
- `-i` `--install` Install the script globally
- `-u` `--uninstall` Uninstall the script globally

### Cron 🕰

If you want to run it every x... you can create a cronjob

###### Example:
Run the script every 5 Min (More details on [cronjobs](http://www.cyberciti.biz/faq/how-do-i-add-jobs-to-cron-under-linux-or-unix-oses/))

1. Edit your cron file with: `crontab -e`
2. Add: `*/5 * * * * ixesha -b /some/folder -o /some/backup/location`
