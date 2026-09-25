# Rewind — closed beta

Thanks for testing. Rewind is a manual trading journal: you log each trade
yourself and it works out whether a setup is actually earning its place, in R.

**Version 0.1.0-beta · Windows 10/11 · about 24 MB**

---

## Download

<https://github.com/HBDZ-boop/TradeJOURNAL/releases/latest>

## Install

1. Download `Rewind-0.1.0-beta-win64.zip`.
2. **Right-click → Extract All.** Don't run it from inside the zip — Windows
   opens zips read-only and the app won't start properly.
3. Put the extracted `Rewind` folder anywhere you like (Documents is fine).
4. Run **`Rewind.exe`**.

There's no installer and nothing is written to Program Files or the registry.
To uninstall, delete the folder.

### "Windows protected your PC"

You'll almost certainly see this on first run. It appears because the app isn't
code-signed — a certificate costs a few hundred a year, which isn't worth it
for a closed beta. It is not a virus warning.

**Click "More info" → "Run anyway".**

You should only see it once per machine.

### If nothing happens when you run it

Rewind draws its window using **WebView2**, which ships with Windows 11 and
recent Windows 10. If the window never appears, you probably don't have it:
install the *Evergreen Standalone Installer* (x64) from
<https://developer.microsoft.com/microsoft-edge/webview2/> and try again.

Tell me if you hit this — I want to know how common it is.

---

## Where your data lives

```
%APPDATA%\Rewind\
    journal.db      every trade you log
    images\         chart screenshots
    exports\        CSVs you export
    logs\           app logs
```

Paste `%APPDATA%\Rewind` into File Explorer's address bar to open it.

**Your data is separate from the app.** Deleting or replacing the Rewind folder
won't touch your journal, and updating to the next beta keeps everything.

**Back it up by copying that folder.** There's no cloud sync — nothing leaves
your machine.

---

## First run

1. Pick a **book** at the top — Demo, Eval, Live or Backtesting. Everything on
   screen is scoped to the selected one. Make your own with **+**.
2. Click **Log trade** (or `Ctrl N`).
3. Type a ticker in the Instrument box and press Enter to add it. The list
   starts empty and fills with what you actually trade.
4. Fill in direction, session, setup, trend alignment and the **result in R**.
   If you'd rather work in prices, open *Prices* and enter entry / stop / exit
   and the R is worked out for you.
5. `Ctrl Enter` saves.

The stats at the top and the Analysis section update as you go. They'll say
"low sample" until about 15 trades — that's honest, not broken. Numbers off
five trades don't mean much.

---

## Exporting

**Export CSV** next to the Trades heading writes the *current* view — the
selected book plus any active filters — to `%APPDATA%\Rewind\exports\` and
opens the folder. Opens cleanly in Excel or Google Sheets.

---

## Sending feedback

Click **?** in the top right:

- **Send feedback** — opens the feedback form. Anything goes: a bug, something
  that felt clumsy, something missing, or something you liked. For a bug, say
  what you were doing, what you expected, and what happened.
- **Open log folder** — attach `rewind.log` to your report if the app
  misbehaved. It records what the app did, never what you traded.

If the app crashes you'll get a dialog offering to open that folder.

Please mention the version (bottom-right corner of the window) in anything you send.

### Most useful to hear about

- Anything that loses or corrupts a trade — highest priority.
- Numbers that look wrong. Say which and what you expected.
- Anything that makes logging slow enough that you'd skip it. The whole app
  depends on being fast at 1am.
- Crashes, freezes, blank windows.

---

## Privacy

Everything stays on your machine. No account, no telemetry by default, no
network calls except an update check against GitHub on launch.

If crash reporting gets switched on in a later build, it sends the error and
where it happened — never your trades, notes, screenshots or file paths. The
toggle is in the **?** menu and you can turn it off.

---

## Known limitations

- Windows only for now.
- Unsigned, so SmartScreen warns once.
- Updates aren't automatic — you'll be told when one exists and given a link.
- One journal at a time; books separate your accounts within it.
