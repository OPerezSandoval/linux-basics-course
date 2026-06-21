# Installation Process

A guide for picking and following a Linux installation method. Choose the option that best fits your needs:

| Method | Best for | Difficulty |
| --- | --- | --- |
| [Docker](#docker) | Quick throwaway Linux shell, learning commands | Easy |
| [VMware Fusion](#vmware-fusion) | Full Linux desktop without touching your hardware | Medium |
| [Cloud (AWS)](#cloud-aws) | Remote server, practicing SSH, no local resources | Medium |
| [Own Hardware](#own-hardware) | Dedicated machine / old laptop, full experience | Advanced |

---

## Docker

1. Download and install Docker Desktop (or just the Docker CLI).
2. Open Docker Desktop and a terminal window.
3. Run the container:
   ```bash
   docker run -it ubuntu:latest bash
   ```

---

## VMware Fusion

1. Download and install VMware Fusion.
2. Download a live ISO (any distro).
3. Open VMware Fusion and install with the defaults.
4. When you start the VM it will prompt you to install — click on it and go through the install process.
5. Once successfully installed, go back to the live station and restart the VM.
6. Once rebooted, go through the setup process: create a username and password.
7. Open a terminal and run `sudo whoami`, enter your password, and confirm you have root access.
8. Turn the SSH service on, then confirm it is active:
   ```bash
   systemctl start --now sshd
   systemctl status sshd
   ```
9. Get the IP of your VM:
   ```bash
   ip a
   ```
10. On your local machine, connect over SSH and enter your password:
    ```bash
    ssh user_name@ip
    ```

---

## Cloud (AWS)

1. Create an AWS account.
2. Create an EC2 instance.
3. Create and save the keypair.
4. Launch the instance.
5. Change permissions on the keypair to `400`:
   ```bash
   chmod 400 keypair.pem
   ```
6. Connect to the instance:
   ```bash
   ssh -i file/path/keypair.pem ec2-user@public-ip/dns
   ```

> **Important:** Make sure to stop the instance when not in use, or terminate it completely.

---

## Own Hardware

1. Download a live ISO (any distro).
2. Download Balena Etcher and flash a USB with the ISO.
3. Get your hardware, plug in the USB, and power on.
4. Get to the bios menu. (Hold F2,F12,F10, Macbook -> option )
5. Boot the correct iso and install 
6. Reboot, remove usb, and finish the setup 
7. Connect through wired ethernet 
8. Run updates 
    ``` bash
    sudo dnf update && sudo dnf upgrade
    ```
9. Turn the SSH service on, then confirm it is active:
   ```bash
   systemctl start --now sshd
   systemctl status sshd
   ```
10. Get the IP of your VM:
   ```bash
   ip a
   ```
11. On your local machine, connect over SSH and enter your password:
    ```bash
    ssh user_name@ip
    ```
12. Install Wifi drivers 
    ```bash
    sudo dnf install https://mirrors.rpmfusion.org/free/fedora/rpmfusion-free-release-$(rpm -E %fedora).noarch.rpm https://mirrors.rpmfusion.org/nonfree/fedora/rpmfusion-nonfree-release-$(rpm -E %fedora).noarch.rpm
    sudo dnf install akmod-wl
    sudo reboot 
    ```
13. Wifi should be enabled to choose and connect
14. Make ip persistent in your router settings 