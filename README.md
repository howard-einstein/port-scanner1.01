# Net Scan Mapper

A desktop IPv4 scanner for checking hosts and networks you own or are authorized
to assess. It provides a Tkinter interface for configuring scans and viewing
results.

## Requirements

- Python 3
- Tkinter, usually included with Python (some Linux distributions package it
  separately)
- `ttkthemes`
- Nmap for scan modes other than TCP connect

Install the Python dependency:

```sh
python3 -m pip install ttkthemes
```

Install Nmap using your operating system's package manager if you plan to use
its scan modes, and make sure `nmap` is available on your `PATH`.

## Run

From this directory, launch the app with:

```sh
python3 net_scan_mapper
```

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
