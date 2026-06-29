# The Linux File System & Navigation

## Core Concept

In Linux, everything is represented as a file ->  directories, devices, processes, network connections. One file system, one tree, everything lives under `/`.

---

## Key Directories

| Directory | What lives here |
| --- | --- |
| `/` | Root — top of everything |
| `/home` | User files and directories |
| `/etc` | System and application config files |
| `/var` | Logs, caches, data that changes over time |
| `/var/log` | System logs |
| `/tmp` | Temporary files that clear on reboot |
| `/proc` | Live kernel and process info  |
| `/dev` | Device files |
| `/bin` | Essential command binaries |
| `/usr` | User programs and data |

---

## Paths

**Absolute** — starts from `/`, always works regardless of where you are:
```bash
/home/omar/projects/script.sh
```

**Relative** — starts from your current location:
```bash
projects/script.sh
```

**Shortcuts:**
```bash
.     # current directory
..    # parent directory (one level up)
~     # your home directory
```

---

## Navigation

```bash
pwd                  # where am I
cd /var/log          # go to an absolute path
cd projects          # go to a relative path
cd                   # go home
cd ~                 # also go home
cd ..                # go up one level
cd -                 # go back to previous directory
```

---

## Viewing Files

```bash
cat /etc/os-release       # print file contents to terminal
cat filename.txt          # read any file
```

---

## Creating Files & Directories

```bash
mkdir projects                        # create a directory
mkdir -p projects/devops/scripts      # create nested dirs in one shot
touch filename.sh                     # create an empty file
```

---

## Copying

```bash
cp file.txt file-backup.txt           # copy a file
cp -r projects/ projects-backup/      # copy a directory recursively
```

---

## Moving & Renaming

```bash
mv file.txt /tmp/file.txt             # move a file
mv oldname.txt newname.txt            # rename a file
mv -i file.txt dest/                  # prompt before overwriting
```

---

## Deleting

```bash
rm file.txt              # delete a file (no confirmation, no undo)
rmdir dirname            # delete an empty directory
rm -r dirname            # delete a directory and everything in it
```

> `rm` is permanent. Always know what you're deleting. When in doubt, `ls` the path first.

> `rm -rf /` - deletes the entire file system. (Modern Linux has safeguards for this) 

---

## Finding Files

```bash
find /home -name "*.sh"           # find by name (wildcard)
find . -name "deploy.sh"          # find from current directory
find /var -type d -name "log"     # find directories named log
find /var/log -size +10M          # find files larger than 10MB
```

---

## Locating Commands

```bash
which ls          # shows where a command binary lives
type cd           # shows what a command is (binary vs shell builtin)
help cd           # get help for shell builtins 
```

---

## Tip

`rmdir` only removes empty directories — you can use it as a safety check before running `rm -r`.

