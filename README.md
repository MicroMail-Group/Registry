# MicroMail Addon Registry 📦

The official community catalog feed for [MicroMail](https://github.com/grimmdev/micromail) WebAssembly (WASM) addons.

## Overview

This repository hosts the public addon index (`registry.json`) fetched by MicroMail server instances to populate the in-app Addon Store.

## Registry Format

`registry.json` serves a JSON document conforming to the following structure:

```json
{
  "version": "1.0.0",
  "updated_at": "2026-11-15T00:00:00Z",
  "addons": [
    {
      "id": "vendor.addon-name",
      "name": "Addon Display Name",
      "version": "1.0.0",
      "runtime": "backend",
      "description": "Short summary of what this addon does.",
      "download_url": "https://github.com/vendor/addon-repo/releases/download/v1.0.0/addon.zip",
      "sha256": "4f53cda18c2baa0c0354bb5f9a3ecbe5ed12ab4d8e11ba873c2f11161202b945",
      "manifest": {
        "id": "vendor.addon-name",
        "name": "Addon Display Name",
        "version": "1.0.0",
        "runtime": "backend",
        "permissions": ["hook:on_inbound_pre_store"]
      }
    }
  ]
}
```

## Submitting an Addon

1. Fork this repository.
2. Build and publish your addon package (containing `addon.json` and WASM/JS assets) as a GitHub Release `.zip`.
3. Calculate the SHA256 checksum of your `.zip` archive.
4. Add your addon entry to `registry.json`.
5. Open a Pull Request for review.
