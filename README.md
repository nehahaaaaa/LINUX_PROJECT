# LINUX_PROJECT

# sysopctl

`sysopctl` is a command-line tool designed to manage system resources and tasks in a Linux environment. It provides functionality to list services, manage system load, check disk usage, monitor processes, analyze logs, and back up system files.

## Features

- **List Running Services**: View all active services on the system.
- **System Load**: Check the current system load.
- **Service Management**: Start and stop services by name.
- **Disk Usage**: View the disk usage of the system.
- **Process Monitor**: Monitor system processes in real-time.
- **Log Analysis**: Analyze system logs for critical errors from the past hour.
- **Backup System Files**: Back up directories to a specified backup location.

## Requirements

- Linux system with systemd for service management.
- Bash 4.0 or later.
- `rsync` for backup functionality.
- `journalctl` for log analysis.
- Root privileges to manage services and perform backups.

## Installation

### Installing via `.deb` Package (Debian/Ubuntu)

1. Clone the repository or download the package:
   ```bash
   git clone <repository-url>
   ```

2. Navigate to the package directory:
   ```bash
   cd sysopctl-package
   ```

3. Install the `.deb` package:
   ```bash
   sudo dpkg -i sysopctl-package.deb
   ```

4. Make sure the script is executable:
   ```bash
   sudo chmod +x /usr/local/bin/sysopctl
   ```

### Installing via Source (Manual Installation)

1. Download the `sysopctl` script from the repository.
2. Move the script to `/usr/local/bin/` and ensure it has execution permissions:
   ```bash
   sudo mv sysopctl /usr/local/bin/
   sudo chmod +x /usr/local/bin/sysopctl
   ```

## Usage

`sysopctl` is used via the command line. Below are the supported commands and their usage:

### List Running Services
```bash
sysopctl service list
```
Displays a list of all active services on the system, similar to `systemctl list-units --type=service`.

### System Load
```bash
sysopctl system load
```
Displays the current system load using the `uptime` command.

### Start a Service
```bash
sysopctl service start <service-name>
```
Starts the specified service. Replace `<service-name>` with the name of the service (e.g., `apache2`).

### Stop a Service
```bash
sysopctl service stop <service-name>
```
Stops the specified service.

### Disk Usage
```bash
sysopctl disk usage
```
Displays disk usage by partition, similar to `df -h`.

### Monitor Processes
```bash
sysopctl process monitor
```
Displays real-time system process activity using `top`.

### Analyze Logs
```bash
sysopctl logs analyze
```
Analyzes system logs for critical issues in the last hour using `journalctl`.

### Backup Files
```bash
sysopctl backup <path>
```
Backs up the specified directory or file to the `/backup/` directory. Replace `<path>` with the directory or file you want to back up.

## Example

To list services:
```bash
sysopctl service list
```

To back up the `/home/user` directory:
```bash
sysopctl backup /home/user
```

## Contributions

Contributions are welcome. Please submit a pull request or open an issue to suggest improvements or report bugs.

## License

This project is licensed under the MIT License.
