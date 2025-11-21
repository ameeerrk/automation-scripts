# JavaScript Scripts

This directory contains Node.js automation scripts for various tasks.

## 📋 Available Scripts

*Scripts will be added here as the collection grows*

## Prerequisites

- Node.js (version 14.0 or higher)
- npm (Node package manager)

## Getting Started

1. Install Node.js dependencies (if required):
```bash
npm install
```

2. Run a script:
```bash
node script_name.js
```

## Script Categories

- **Web Automation**: Scripts for web scraping and browser automation
- **API Testing**: Scripts for testing REST APIs and endpoints
- **Build Automation**: Scripts for build processes and deployment
- **File Processing**: Scripts for file manipulation and transformation
- **Development Tools**: Scripts to enhance development workflows

## Best Practices

- Always read the script's README before running
- Check for required environment variables
- Install dependencies with `npm install` before running
- Use `npm ci` for clean installs in CI/CD environments
- Keep Node.js and npm up to date

## Common Setup

### Installing dependencies:
```bash
# Install all dependencies
npm install

# Install a specific package
npm install package-name
```

### Running scripts:
```bash
# Run directly with node
node script_name.js

# If configured in package.json scripts
npm run script-name
```

### Environment Variables:
Many scripts use environment variables. Create a `.env` file:
```bash
# .env file example
API_KEY=your-api-key
API_URL=https://api.example.com
```

## Package Management

Scripts may include a `package.json` file. To use:

```bash
# Install dependencies
npm install

# Run a script defined in package.json
npm run script-name

# Update dependencies
npm update
```

## Compatibility

Scripts are designed to work with:
- Node.js 14.x and higher
- Modern JavaScript (ES6+)

Script-specific requirements are noted in individual READMEs.

## Need Help?

If you encounter issues:
1. Check the script's individual README
2. Verify your Node.js version: `node --version`
3. Ensure all dependencies are installed: `npm install`
4. Check for missing environment variables
5. Open an issue if the problem persists
