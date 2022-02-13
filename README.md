<p align="center">
    <img src="https://github.com/rsusik/simple-web-based-interface-for-scanner/raw/main/logo.svg" style="background: white; border-radius: 30pt; border: 5pt solid black" alt="StaticPIE"  width="150" />
</p>
<p align="center">
    <em>Simple Web-based Interface for Scanner</em>
</p>

<p align="center" style="margin-top: 20pt;">
    <img src="https://github.com/rsusik/simple-web-based-interface-for-scanner/raw/main/screenshots/04-cropping.png" width="300">
</p>

This is simple web-based interface for scanner. It allows share the scanner via IP address which makes it accessible by web browser. The frontend interface allows user to crop the image as well as browse previousely scanned images.

From technical perspective it is simply SANE scanimage wrapper. There are quite many things to do to make it production (see TODO section).

## Requirements

- Linux
- SANE (Scanner Access Now Easy) properly configured (`scanimage` tool)
- Python >= 3.8
- [Optionally] NPM (for frontend app building)

## Install and run (local user)
```
pip install swis
swis --ip localhost --port 5520
```
**❗IMPORTANT❗** Change the IP (`localhost` above) to a proper host IP address if you want to access the scanner from other computers (or other devices).

## Install and run (system service)

### Prerequisites
This process requires root privileges, and you need to have Python>=3.8 installed. Also, there is the possibility that the server variants the system doesn't have `pip` installed by default. In this case, execute below::

Fedora (and similar): `sudo dnf install python3-pip`
Ubuntu (and similar): `sudo apt-get install python3-pip`

### Install and start service

```
sudo pip3 install swis
sudo swis --ip [HOST IP ADDRESS] --port 5520 service install -u [USER] -g [GROUP]
sudo swis service start
```

You can check the status by running: `sudo swis service status`

**❗IMPORTANT❗** Change the IP (`[HOST IP ADDRESS]` above) to a proper host IP address.


## Screenshots

### Welcome screen
<img src="https://github.com/rsusik/simple-web-based-interface-for-scanner/raw/main/screenshots/01-welcome-screen.png" width="300">

### Scanning parameters
<img src="https://github.com/rsusik/simple-web-based-interface-for-scanner/raw/main/screenshots/02-scanning-params.png" width="300">

### Scanning in progress
<img src="https://github.com/rsusik/simple-web-based-interface-for-scanner/raw/main/screenshots/03-scanning-progress.png" width="300">

### Cropping scanned image
<img src="https://github.com/rsusik/simple-web-based-interface-for-scanner/raw/main/screenshots/04-cropping.png" width="300">

### Side menu
<img src="https://github.com/rsusik/simple-web-based-interface-for-scanner/raw/main/screenshots/05-menu.png" width="300">

### List of scanned images
<img src="https://github.com/rsusik/simple-web-based-interface-for-scanner/raw/main/screenshots/06-list.png" width="300">


## TODO:

- [ ] error handling
- [x] pip package
- [x] automatically add service with `systemctl`
- [ ] better user interface (i.e. image remove button)
- [ ] move actions to vuex
