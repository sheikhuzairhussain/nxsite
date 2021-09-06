<p align="center">
<br><br>
<img src="https://raw.githubusercontent.com/sheikhuzairhussain/nxsite/d0e682af867c028ab0c03d97483e55eb2b844a7c/nxsite.png" width="30%">
</p>
<br>
NXSite is a minimalistic site manager for NGINX. Works on most Linux-based systems. Heavily inspired by Apache's  <code>a2ensite</code> and <code>a2dissite</code> utilities.

## Installation
```bash
sudo wget https://raw.githubusercontent.com/sheikhuzairhussain/nxsite/main/nxsite -P /usr/bin/
sudo chmod +x /usr/bin/nxsite
```
## Usage
To list all/available sites:
```bash
nxsite list [all|enabled]
```
To enable/disable a site:
```bash
nxsite [up|down] <site-config-name>
```

## Example
To list enabled sites:
```bash
nxsite list enabled
```
To enable <code>example.com</code>
```bash
nxsite up example.com
```
