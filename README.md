# LXC PCNS Template for Proxmox

This repository provides an LXC template for running PowerChute Network Shutdown (PCNS) inside a Proxmox LXC container.

## Features
- Preconfigured Ubuntu/Debian-based LXC template
- Optimized for running PCNS with minimal resources
- Network and security optimizations for Proxmox

## Requirements
- Proxmox VE (latest version recommended)
- APC UPS with Network Management Card (NMC)
- Internet connection for downloading packages

## Installation
1. Clone this repository or download the LXC template.
2. Import the LXC template into Proxmox:
   ```sh
   pct create <vmid> /path/to/lxc-template.tar.gz -storage <storage>
   ```
3. Start the container:
   ```sh
   pct start <vmid>
   ```
4. Configure PCNS to communicate with your APC UPS NMC.
   Access the PCNS web interface via https://<container-ip>:6547

## Configuration
- Ensure the correct network bridge is assigned.
- Modify firewall rules to allow communication with the UPS.
- Adjust container resources as needed.

## Troubleshooting
Check logs for issues with:
```sh
journalctl -u pcns -f
```

## Contributing
Pull requests and suggestions are welcome!

## License
This project is licensed under the MIT License.

