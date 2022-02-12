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

## Install and run from pip (RECOMMENDED)
```
pip install swis
python -m swis --ip localhost --port 5520
```
**❗IMPORTANT❗** Change the IP (`localhost` above) to a proper host IP address if you want to access the scanner from other computers (or other devices).

## Build app

```
sh build.sh
```

## Run (from source code)

1. Download the latest release from: https://github.com/rsusik/simple-web-based-interface-for-scanner/releases 
2. Run below command (extracts, installs dependencies and executes):

```
mkdir -p swis && \
tar -C swis -xvzf swis.tar.gz && \
cd swis && \
pip install -r requirements.txt && \
python swis.py --ip localhost --port 5520
```

3. Then you can access the scanner through http://localhost:5520

**❗IMPORTANT❗** Change the IP (`localhost` above) to appropriate host IP address of the host if you want to access the scanner from other computers (or other devices).


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
- [ ] automatically add service with `systemctl`
- [ ] better user interface (i.e. image remove button)
- [ ] move actions to vuex
