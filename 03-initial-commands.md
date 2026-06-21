# Your First Commands + First Customization

## Aliases & `.bashrc`

Create a shortcut for a command:
```bash
alias cl=clear
alias celar=clear
```

Make it permanent — add the aliases to your `.bashrc`:
```bash
vim ~/.bashrc
```

Apply the changes without restarting your terminal:
```bash
source ~/.bashrc
```

Now `cl` and `celar` both clear your screen.

---

## Commands

| Command | What it does |
| --- | --- |
| `whoami` | Shows your current user |
| `hostname` | Shows the machine name |
| `pwd` | Shows your current directory |
| `ls` | Lists files and folders |
| `echo` | Prints text or variable values |
| `date` | Shows current date and time |
| `uname -a` | Shows OS and kernel info |
| `uptime` | Shows how long the system has been running |
| `history` | Shows previously run commands |
| `man <command>` | Opens the manual for a command |
| `<command> --help` | Quick reference for a command |

---

## Useful `ls` flags

```bash
ls -la        # long format + hidden files
ls /          # list root of the filesystem
ls /etc       # list a specific directory
```

## Useful `echo` examples

```bash
echo "Hello"
echo $USER    # prints your username
echo $HOME    # prints your home directory path
```

---

## Tip

Use `man` and `--help` before googling. The answer is almost always already on your machine.
