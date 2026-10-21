# Net Scan Mapper

A desktop IPv4 scanner for checking hosts and networks you own or are authorized
to assess. It provides a Tkinter interface for configuring scans and viewing
results.

## Requirements

All platforms need Python 3 with Tkinter. Nmap is optional for TCP connect
scans, but required for the other scan modes. The app uses `ttkthemes` for its
interface.

### Windows

1. Install Python 3 from [python.org](https://www.python.org/downloads/windows/),
   and enable the option to add Python to `PATH`.
2. Confirm Tkinter is available by running `py -m tkinter` in PowerShell. A
   small test window should open.
3. To use Nmap scan modes, install Nmap from
   [nmap.org](https://nmap.org/download.html) and make sure `nmap` is available
   on `PATH`.

Open PowerShell in the project folder and run:

```powershell
py -3 -m venv .venv
.venv\Scripts\Activate.ps1
python -m pip install ttkthemes
python net_scan_mapper
```

If PowerShell blocks virtual-environment activation, use Command Prompt and
activate with `.venv\Scripts\activate.bat` instead.

### macOS

1. Install Python 3, for example from
  [python.org](https://www.python.org/downloads/macos/). Its installer includes
  Tkinter. Confirm it works by running `python3 -m tkinter` in Terminal; a
  small test window should open.
2. To use Nmap scan modes, install [Homebrew](https://brew.sh/) and run
  `brew install nmap`, or install Nmap using another trusted method. Make sure
  `nmap` is available on `PATH`.

In Terminal, change to the project folder and run:

```sh
python3 -m venv .venv
source .venv/bin/activate
python -m pip install ttkthemes
python net_scan_mapper
```

### Linux

Install Python 3 and Tkinter using your distribution's package manager. For
example, Debian and Ubuntu users can run `sudo apt install python3 python3-tk`.
Install Nmap from the package manager if you plan to use its scan modes, and
make sure `nmap` is available on `PATH`.

From the project folder, create and activate a virtual environment, install the
Python dependency, and launch the app:

```sh
python3 -m venv .venv
source .venv/bin/activate
python -m pip install ttkthemes
python net_scan_mapper
```

## Run

After installing the requirements and activating the virtual environment,
launch the app from the project folder with `python net_scan_mapper`.

The virtual environment only needs to be created and the dependency installed
once. Activate it again each time before launching the app. On Windows, use
PowerShell's `.venv\Scripts\Activate.ps1` or Command Prompt's
`.venv\Scripts\activate.bat`.

## Using the app

Enter an IPv4 address, hostname, or IPv4 subnet. Choose a port or port range
where applicable, then select a scan type. TCP connect scans run directly in
Python; SYN, ACK, UDP, IP protocol, host discovery (ping), service version, and
OS detection scans use Nmap. Idle scan is shown as unavailable.

The defaults are `127.0.0.1`, ports `1-1024`, 100 threads, and a 0.5-second
timeout for TCP connect scans. Results show open ports by default; use “Show
only open ports” to change that where supported. Scan results are displayed in
the window and are not saved automatically. Some Nmap modes may require
additional privileges depending on the operating system and scan type.

Only scan systems and networks for which you have permission. Scanning can
generate network traffic and may be restricted by local policy or law.
