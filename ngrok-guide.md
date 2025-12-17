# ngrok Quick Start Guide

## Installation

Download ngrok from [https://ngrok.com/download](https://ngrok.com/download) and extract the archive.

### Mac Setup

1. Move the `ngrok` binary to `/usr/local/bin/`, or add the directory containing ngrok to your PATH
2. To add to PATH, edit `~/.zshrc` or `~/.bash_profile` and add: `export PATH="$PATH:/path/to/ngrok"`
3. Restart your terminal or run `source ~/.zshrc` (or `source ~/.bash_profile`)

### Windows Setup

1. Extract `ngrok.exe` to a folder (e.g., `C:\ngrok`)
2. Add the directory to your system PATH:
   - Open System Properties > Environment Variables
   - Edit the "Path" variable under System Variables
   - Add the path to your ngrok directory
3. Restart your terminal/command prompt

## Usage

Once ngrok is installed and in your PATH, you can expose your local server. For a server running on port 3000, use one of these commands:

```bash
ngrok http 3000 --host-header="localhost:3000"
```

or

```bash
ngrok http --host-header=rewrite 3000
```

Both commands will create a public URL that tunnels to your local server. The `--host-header` flag ensures proper routing of requests.

