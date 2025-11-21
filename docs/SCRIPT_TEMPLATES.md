# Script Template Guide

This guide provides templates for creating new scripts in this repository. Following these templates ensures consistency and makes scripts easier to understand and maintain.

## Python Script Template

```python
#!/usr/bin/env python3
"""
Script Name: script_name.py
Description: Brief description of what the script does
Author: Your Name (@your-github-username)
Created: YYYY-MM-DD
Version: 1.0.0
"""

import argparse
import logging
import sys
from typing import Optional

# Configure logging
logging.basicConfig(
    level=logging.INFO,
    format='%(asctime)s - %(levelname)s - %(message)s'
)
logger = logging.getLogger(__name__)


def main(args: argparse.Namespace) -> int:
    """
    Main function.
    
    Args:
        args: Command line arguments
        
    Returns:
        Exit code (0 for success, non-zero for failure)
    """
    try:
        logger.info("Starting script execution")
        
        # Your main logic here
        
        logger.info("Script completed successfully")
        return 0
        
    except Exception as e:
        logger.error(f"Error: {e}")
        return 1


def parse_arguments() -> argparse.Namespace:
    """Parse command line arguments."""
    parser = argparse.ArgumentParser(
        description='Script description'
    )
    parser.add_argument(
        '-i', '--input',
        required=True,
        help='Input parameter description'
    )
    parser.add_argument(
        '-v', '--verbose',
        action='store_true',
        help='Enable verbose output'
    )
    return parser.parse_args()


if __name__ == '__main__':
    args = parse_arguments()
    
    if args.verbose:
        logger.setLevel(logging.DEBUG)
    
    sys.exit(main(args))
```

## Bash Script Template

```bash
#!/bin/bash
#
# Script Name: script_name.sh
# Description: Brief description of what the script does
# Author: Your Name (@your-github-username)
# Created: YYYY-MM-DD
# Version: 1.0.0
#

set -euo pipefail  # Exit on error, undefined variable, or pipe failure

# Color codes for output
readonly RED='\033[0;31m'
readonly GREEN='\033[0;32m'
readonly YELLOW='\033[1;33m'
readonly NC='\033[0m' # No Color

# Script directory
readonly SCRIPT_DIR="$(cd "$(dirname "${BASH_SOURCE[0]}")" && pwd)"

# Default values
VERBOSE=false
DRY_RUN=false

#######################################
# Print error message and exit
# Arguments:
#   Error message
#######################################
error() {
    echo -e "${RED}ERROR: $1${NC}" >&2
    exit 1
}

#######################################
# Print info message
# Arguments:
#   Info message
#######################################
info() {
    echo -e "${GREEN}INFO: $1${NC}"
}

#######################################
# Print warning message
# Arguments:
#   Warning message
#######################################
warn() {
    echo -e "${YELLOW}WARNING: $1${NC}"
}

#######################################
# Print usage information
#######################################
usage() {
    cat << EOF
Usage: $(basename "$0") [OPTIONS]

Description of what the script does.

OPTIONS:
    -h, --help      Display this help message
    -v, --verbose   Enable verbose output
    -d, --dry-run   Perform a dry run without making changes
    
EXAMPLES:
    $(basename "$0") --verbose
    $(basename "$0") --dry-run

EOF
}

#######################################
# Main function
#######################################
main() {
    info "Starting script execution"
    
    # Your main logic here
    
    info "Script completed successfully"
}

# Parse command line arguments
while [[ $# -gt 0 ]]; do
    case $1 in
        -h|--help)
            usage
            exit 0
            ;;
        -v|--verbose)
            VERBOSE=true
            shift
            ;;
        -d|--dry-run)
            DRY_RUN=true
            shift
            ;;
        *)
            error "Unknown option: $1"
            ;;
    esac
done

# Run main function
main
```

## JavaScript Script Template

```javascript
#!/usr/bin/env node

/**
 * Script Name: script_name.js
 * Description: Brief description of what the script does
 * Author: Your Name (@your-github-username)
 * Created: YYYY-MM-DD
 * Version: 1.0.0
 */

const fs = require('fs');
const path = require('path');

// Configuration
const CONFIG = {
    verbose: false,
    dryRun: false
};

/**
 * Log info message
 * @param {string} message - Message to log
 */
function info(message) {
    console.log(`[INFO] ${message}`);
}

/**
 * Log error message
 * @param {string} message - Error message
 */
function error(message) {
    console.error(`[ERROR] ${message}`);
}

/**
 * Log warning message
 * @param {string} message - Warning message
 */
function warn(message) {
    console.warn(`[WARN] ${message}`);
}

/**
 * Main function
 * @returns {Promise<number>} Exit code
 */
async function main() {
    try {
        info('Starting script execution');
        
        // Your main logic here
        
        info('Script completed successfully');
        return 0;
    } catch (err) {
        error(`Script failed: ${err.message}`);
        if (CONFIG.verbose) {
            console.error(err.stack);
        }
        return 1;
    }
}

/**
 * Parse command line arguments
 * @returns {Object} Parsed arguments
 */
function parseArguments() {
    const args = process.argv.slice(2);
    const parsed = {};
    
    for (let i = 0; i < args.length; i++) {
        const arg = args[i];
        switch (arg) {
            case '-h':
            case '--help':
                printUsage();
                process.exit(0);
                break;
            case '-v':
            case '--verbose':
                CONFIG.verbose = true;
                break;
            case '-d':
            case '--dry-run':
                CONFIG.dryRun = true;
                break;
            default:
                error(`Unknown option: ${arg}`);
                process.exit(1);
        }
    }
    
    return parsed;
}

/**
 * Print usage information
 */
function printUsage() {
    console.log(`
Usage: node ${path.basename(__filename)} [OPTIONS]

Description of what the script does.

OPTIONS:
    -h, --help      Display this help message
    -v, --verbose   Enable verbose output
    -d, --dry-run   Perform a dry run without making changes

EXAMPLES:
    node ${path.basename(__filename)} --verbose
    node ${path.basename(__filename)} --dry-run
    `);
}

// Entry point
if (require.main === module) {
    parseArguments();
    main().then(exitCode => {
        process.exit(exitCode);
    });
}

module.exports = { main };
```

## PowerShell Script Template

```powershell
<#
.SYNOPSIS
    Brief description of what the script does

.DESCRIPTION
    Detailed description of the script's functionality

.PARAMETER InputPath
    Description of the input parameter

.PARAMETER Verbose
    Enable verbose output

.EXAMPLE
    .\script_name.ps1 -InputPath "C:\path"
    Description of this example

.EXAMPLE
    .\script_name.ps1 -InputPath "C:\path" -Verbose
    Description of this example with verbose output

.NOTES
    File Name   : script_name.ps1
    Author      : Your Name (@your-github-username)
    Created     : YYYY-MM-DD
    Version     : 1.0.0
    Requires    : PowerShell 5.1 or higher
#>

[CmdletBinding()]
param(
    [Parameter(Mandatory=$true)]
    [string]$InputPath,
    
    [Parameter(Mandatory=$false)]
    [switch]$DryRun
)

# Set strict mode
Set-StrictMode -Version Latest
$ErrorActionPreference = "Stop"

#region Functions

function Write-Info {
    param([string]$Message)
    Write-Host "[INFO] $Message" -ForegroundColor Green
}

function Write-Error {
    param([string]$Message)
    Write-Host "[ERROR] $Message" -ForegroundColor Red
}

function Write-Warning {
    param([string]$Message)
    Write-Host "[WARN] $Message" -ForegroundColor Yellow
}

function Main {
    try {
        Write-Info "Starting script execution"
        
        # Your main logic here
        
        Write-Info "Script completed successfully"
        return 0
    }
    catch {
        Write-Error "Script failed: $_"
        if ($VerbosePreference -eq 'Continue') {
            Write-Error $_.ScriptStackTrace
        }
        return 1
    }
}

#endregion

# Entry point
$exitCode = Main
exit $exitCode
```

## Script README Template

Every script should have its own README.md file:

```markdown
# Script Name

Brief one-line description of what the script does.

## Description

Detailed description of the script's functionality, including:
- What problem it solves
- How it works
- Any important implementation details

## Prerequisites

- Requirement 1 (e.g., Python 3.7+)
- Requirement 2 (e.g., specific library)
- Requirement 3 (e.g., API credentials)

## Installation

```bash
# Step-by-step installation instructions
pip install -r requirements.txt
```

## Configuration

If the script requires configuration:

```bash
# Create config file
cp config.example.json config.json

# Edit with your settings
nano config.json
```

## Usage

Basic usage:
```bash
python script_name.py --input data.txt --output result.txt
```

### Options

- `--input, -i`: Input file path (required)
- `--output, -o`: Output file path (optional, default: stdout)
- `--verbose, -v`: Enable verbose output
- `--help, -h`: Display help message

### Examples

Example 1: Basic usage
```bash
python script_name.py --input data.txt
```

Example 2: With verbose output
```bash
python script_name.py --input data.txt --verbose
```

Example 3: Custom output
```bash
python script_name.py --input data.txt --output result.txt
```

## Output

Description of what the script outputs and in what format.

## Known Limitations

- Limitation 1
- Limitation 2

## Troubleshooting

Common issues and solutions:

### Issue 1
**Problem**: Description of the problem
**Solution**: How to fix it

### Issue 2
**Problem**: Description of the problem
**Solution**: How to fix it

## Contributing

See [CONTRIBUTING.md](../../CONTRIBUTING.md) for guidelines.

## License

This script is licensed under the MIT License - see [LICENSE](../../LICENSE).

## Author

Your Name (@your-github-username)

## Version History

- 1.0.0 (YYYY-MM-DD): Initial release
```

## Best Practices

When creating scripts, follow these best practices:

1. **Documentation**: Always include comprehensive comments and documentation
2. **Error Handling**: Implement proper error handling and validation
3. **Logging**: Use appropriate logging levels (INFO, WARNING, ERROR)
4. **Arguments**: Use argument parsers for command-line scripts
5. **Exit Codes**: Return appropriate exit codes (0 for success, non-zero for errors)
6. **Security**: Never hardcode credentials or sensitive data
7. **Testing**: Test scripts thoroughly before committing
8. **Compatibility**: Specify version requirements and dependencies
9. **Clean Code**: Follow language-specific style guidelines
10. **Modularity**: Break complex logic into functions

## Naming Conventions

- **Python**: Use snake_case (e.g., `my_script.py`)
- **Bash**: Use kebab-case or snake_case (e.g., `my-script.sh` or `my_script.sh`)
- **JavaScript**: Use camelCase or kebab-case (e.g., `myScript.js` or `my-script.js`)
- **PowerShell**: Use PascalCase for function names, kebab-case for files (e.g., `My-Script.ps1`)

## Additional Resources

- [Python Style Guide (PEP 8)](https://www.python.org/dev/peps/pep-0008/)
- [Bash Best Practices](https://bertvv.github.io/cheat-sheets/Bash.html)
- [JavaScript Style Guide](https://github.com/airbnb/javascript)
- [PowerShell Best Practices](https://poshcode.gitbook.io/powershell-practice-and-style/)
