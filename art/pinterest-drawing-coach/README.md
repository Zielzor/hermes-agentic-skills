# Pinterest Drawing Coach for Hermes Agent

This custom Hermes skill asks Hermes to discover easy drawing references on Pinterest and convert them into achievable pen-and-ink practice sessions. It can fall back to Pinterest search links when individual pins are inaccessible.

## Install on Windows (PowerShell)

1. Download `hermes-pinterest-drawing-coach.zip` from ChatGPT into your Downloads folder.
2. Run:

   ```powershell
   Expand-Archive -LiteralPath "$env:USERPROFILE\Downloads\hermes-pinterest-drawing-coach.zip" -DestinationPath "$env:USERPROFILE\.hermes\skills" -Force
   ```

3. Configure a search provider if needed: run `hermes tools`, select **Web Search & Extract**, and choose a backend. Current Hermes documentation includes keyless DDGS as a web-search option. Browsing Pinterest interactively is optional and may require configured Hermes browser tools; Pinterest access is not guaranteed.
4. Start a new Hermes session and test:

   ```text
   /pinterest-drawing-coach Find 5 easy Pinterest architecture sketches and give me one 20-minute EF fountain-pen cross-hatching exercise.
   ```

## Install on macOS / Linux

Unzip `hermes-pinterest-drawing-coach.zip` into `~/.hermes/skills/`, keeping the `art/pinterest-drawing-coach/SKILL.md` directory structure. Start a new Hermes session and use `/pinterest-drawing-coach`.

## Verify

Run `hermes skills list` and look for `pinterest-drawing-coach`. If missing, confirm the `SKILL.md` path and begin a new Hermes session.

## Files

- `SKILL.md`: complete reusable skill; no additional scripts, model, credentials, or Pinterest API integration are bundled.

This package does not install the skill onto your computer automatically and has not been executed inside your local Hermes installation.
