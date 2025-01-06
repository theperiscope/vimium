# Build & Package

`make.js` script is only partially platform-agnostic. the `package` command **does not** work on Windows.

As a workaround, WSL is used. To package:

1. Start WSL from folder with _make.js_ script: `wsl`
1. Execute package command: deno --allow-read --allow-write --allow-env --allow-net --allow-run --allow-sys make.js package
1. Review output in `dist` folder

## Installing *deno* in WSL

```bash
# deno requires unzip
sudo apt-get install unzip -y

# make.js requires zip
sudo apt-get install zip -y

# install deno; choose defaults
curl -fsSL https://deno.land/install.sh | sh
```

## Deployment to *Firefox Developer Hub*

1. Login to https://addons.mozilla.org/en-US/developers/addons
1. Backup latest Vimium extension settings
1. From `dist/firefox` upload the zip file as *new version*
1. Wait for approval (https://addons.mozilla.org/en-US/developers/addon/dafa47951eba4c1c8dfa/versions)
1. Click on the latest approved version
1. Near top, click the xpi link to install in Firefox
