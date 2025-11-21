# Bash Scripts

This directory contains shell scripts for Unix/Linux automation tasks.

## 📋 Available Scripts

*Scripts will be added here as the collection grows*

## Prerequisites

- Bash shell (version 4.0 or higher recommended)
- Standard Unix/Linux utilities (grep, sed, awk, etc.)
- Appropriate permissions to execute scripts

## Getting Started

1. Make scripts executable:
```bash
chmod +x script_name.sh
```

2. Run the script:
```bash
./script_name.sh
```

## Script Categories

- **System Administration**: Scripts for system management and maintenance
- **File Operations**: Scripts for file manipulation and organization
- **Backup & Sync**: Scripts for data backup and synchronization
- **Development Tools**: Scripts to aid in development workflows
- **Network Utilities**: Scripts for network operations and monitoring

## Best Practices

- Always review scripts before executing them
- Test scripts in a safe environment first
- Check script permissions: `ls -l script_name.sh`
- Make scripts executable with: `chmod +x script_name.sh`
- Use `bash -n script_name.sh` to check syntax without running

## Common Usage Patterns

### Running with arguments:
```bash
./script_name.sh arg1 arg2
```

### Running with sudo (if required):
```bash
sudo ./script_name.sh
```

### Scheduling with cron:
```bash
# Edit crontab
crontab -e

# Add a line like this to run daily at 2am:
0 2 * * * /path/to/script_name.sh
```

## Compatibility

Most scripts are designed to work on:
- Linux (Ubuntu, Debian, CentOS, RHEL)
- macOS
- WSL (Windows Subsystem for Linux)

Script-specific compatibility notes are included in individual READMEs.

## Need Help?

If you encounter issues:
1. Check the script's individual README
2. Verify your bash version: `bash --version`
3. Ensure all required utilities are installed
4. Check script permissions
5. Open an issue if the problem persists
