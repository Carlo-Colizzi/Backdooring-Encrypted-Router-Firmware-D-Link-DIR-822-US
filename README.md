# Backdooring Encrypted Router Firmware D-Link-DIR-822-US

## Project Overview
This project focuses on the security analysis and modification of the encrypted firmware of the **D-Link DIR-822-US** router. The main goal was to understand the firmware protection mechanisms, extract and decrypt the firmware, and assess the feasibility of injecting custom modifications for research purposes.

## Methodology
### 1. Information Gathering (OSINT)
The research began with gathering information on the firmware history of the target router. By analyzing publicly available sources, it was determined that earlier firmware versions were not encrypted. This discovery guided the approach to firmware extraction and decryption.

### 2. Firmware Extraction and Analysis
To analyze the firmware structure, various techniques were used:
- Downloading different firmware versions from D-Link’s FTP server.
- Extracting firmware images to compare structural changes over different releases.
- Identifying encryption mechanisms by measuring entropy variations between versions.

### 3. Decryption Process
Once encryption was identified as a security measure, the project aimed to locate the decryption key. By analyzing system scripts and binary files within the firmware, it was possible to extract the key used for decryption. This allowed for full access to the decrypted firmware image.

### 4. Modifying and Rebuilding the Firmware
With the decrypted firmware accessible, modifications were introduced. The key steps included:
- Injecting a custom payload within the extracted file system.
- Adjusting system startup scripts to ensure persistence of modifications.
- Rebuilding the firmware while ensuring size constraints were respected.

### 5. Deployment and Testing
The modified firmware was tested in a controlled environment using:
- Emulation tools to simulate execution.
- Firmware deployment onto a real device.
- Network monitoring to validate the behavior of the injected modifications.

## Tools Used
- **Binwalk** – Firmware extraction and analysis.
- **Ghidra** – Reverse engineering and static analysis of binaries.
- **qemu-mips** – Emulation of the router’s MIPS architecture.
- **Buildroot** – Cross-compilation of custom modifications.
- **Firmware Analysis Toolkit** – Virtualized testing environment.

## Ethical Considerations
This project is intended solely for educational and cybersecurity research purposes. Any unauthorized use, deployment, or modification of firmware on production devices without explicit permission may violate legal and ethical guidelines.

## Author
Carlo Colizzi
