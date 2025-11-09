# FunPilot Root Domain Repository

This repository controls the **root domain** for `funpilot-sport.github.io`.

## Purpose

Both Android and iOS deep link verification check at the domain root:
- **Android App Links**: `https://funpilot-sport.github.io/.well-known/assetlinks.json`
- **iOS Universal Links**: `https://funpilot-sport.github.io/.well-known/apple-app-site-association`

This repository provides these critical files to enable automatic deep link verification for both:
- **Production app** (`com.konfetti.funpilot`)
- **Development app** (`com.konfetti.funpilot.dev`)

## Files

- `/.well-known/assetlinks.json` - Android Digital Asset Links file for both app flavors
- `/.well-known/apple-app-site-association` - iOS Universal Links file for both app flavors (TEAMID placeholder)
- `/.nojekyll` - Disables Jekyll so GitHub Pages serves dotfiles
- `/_headers` - Sets correct Content-Type for both .well-known files
- `/index.html` - Redirects visitors to main landing page at `/funpilot/`

## Deployment

Any changes to verification files (e.g., new signing key, Apple Team ID) must be committed and pushed to take effect.

Wait 1-2 minutes after pushing for GitHub Pages to deploy, then verify:
```
https://funpilot-sport.github.io/.well-known/assetlinks.json
https://funpilot-sport.github.io/.well-known/apple-app-site-association
```

## Related Repositories

- `funpilot` - Production landing page at `/funpilot/`
- `funpilot-dev` - Development landing page at `/funpilot-dev/`
