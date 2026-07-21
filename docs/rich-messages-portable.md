# AyuGram Rich Messages Portable

This branch contains a personal portable Windows x64 package workflow for AyuGram Desktop 7.0.3 with Telegram Rich Messages support.

## Required GitHub Secrets

Add these repository secrets before running the portable workflow:

- `TDESKTOP_API_ID`
- `TDESKTOP_API_HASH`

GitHub path:

`Settings` -> `Secrets and variables` -> `Actions` -> `New repository secret`

The workflow intentionally fails when these secrets are missing. A test API build is not useful for a personal production Telegram account.

## Workflow

Run:

`Actions` -> `Rich Messages Portable Windows x64` -> `Run workflow`

Artifact name:

`AyuGram-RichMessages-Portable-Windows-x64`

## Portable layout

The artifact contains:

- `AyuGram.exe`
- optional `Updater.exe`, if the build produces it
- `RUN_PORTABLE.bat`
- empty `tdata/`
- `README-PORTABLE.txt`

Start with `RUN_PORTABLE.bat`. It launches AyuGram with `-workdir` pointing to the local `tdata` folder, so account data stays inside the portable directory and does not mix with a normal Telegram or AyuGram install.

## Build options

The portable workflow builds Release x64 with:

- Telegram Desktop 7.0.3 base
- Rich Messages / InputRichMessage support
- AyuGram branding and AppId restored
- auto-update disabled
- crash reports disabled

## Manual checks before personal use

- Login works.
- Existing Rich Message / article opens correctly.
- New article can be created and sent.
- Existing article can be edited.
- Draft article survives restart.
- Ghost mode still works.
- Anti-recall / saved deleted messages still works.
- Message history and filters still work.
