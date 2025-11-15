# Noctis-round-Transparent (Custom KDE Plasma Theme)
Backup and full restoration guide for the customized *Noctis-round-Custom* Plasma theme.

This package contains all modified SVG assets responsible for:
- True transparency (0% opacity) on the Plasma panel
- Removal of shadows, gradients and background overlays
- Preservation of the original Noctis-Round rounded visuals
- Full compatibility with KDE Plasma 6.5+
- Integration with KWin Rounded Corners script

This backup allows restoring the exact visual configuration in case of:
- Theme corruption  
- KDE update overwriting local files  
- Plasma cache regeneration  
- Manual edits gone wrong  

---

## 📁 Included in this Backup
Noctis-round-Custom/
├── widgets/
│ ├── panel-background.svg ← manually edited transparency
│ ├── other modified widgets…
└── metadata.desktop or metadata.json
README.md

yaml
Copiar código

All changes were applied directly to SVG files using manual editing.  
No automated patching tools were used in order to avoid unwanted artifacts.

---

## 🚀 Installation (Restore Procedure)

### 1. Remove previous versions (to avoid conflicts)
```bash
rm -rf ~/.local/share/plasma/desktoptheme/Noctis-round-Custom
2. Copy the backup theme to the correct KDE directory
bash
Copiar código
cp -r "/home/mr_blue/Área de Trabalho/Noctis-Round-Transparent-Backup/Noctis-round-Custom" ~/.local/share/plasma/desktoptheme/
3. Apply the theme in KDE Plasma
Open System Settings

Go to Appearance → Plasma Style

Select Noctis-round-Custom

Apply

🎨 Important: Disable KDE Background Contrast Enhancer
This theme uses real transparency, so KDE’s built-in contrast system may interfere.

Disable it here:

System Settings → Appearance → Style → Effects → “Increase background contrast” (disable)

If this option remains enabled, KDE may:

Add unwanted gray tint

Reduce transparency

Overlay shadows or blur

🔧 Optional: Restart KWin (if visual glitches appear)
bash
Copiar código
DISPLAY=:0 kwin_x11 --replace & disown
This forces KWin to reload the decorations and SVG assets without rebooting.

🧩 KWin Rounded Corners Integration
For best visual results, ensure that the KWin script “Rounded Corners” (or similar) is installed and active:

Check:

bash
Copiar código
kpackagetool6 -t KWin/Script --list
Enable (via System Settings):

sql
Copiar código
System Settings → Window Management → KWin Scripts → Rounded Corners
This preserves rounded borders on transparent panels.

🔍 Notes About the SVG Modifications
The panel-background.svg and related widget assets were modified to:

Remove all opacity, shadow and gradient layers

Set fill, stroke and overlays to fully transparent

Remove blur filters and extra contrast

Keep geometry and metadata intact

Preserve KDE hints (hint-top-margin, hint-bottom-margin, etc.)

Only the color-affecting attributes were changed:

opacity

fill-opacity

stroke-opacity

shadow/blur filters

gradient opacity stops

All other content remains original to avoid breaking theme structure.

🛠 Updating the Theme (Advanced)
If KDE updates overwrite theme assets:

Re-copy this backup again

Reapply the theme

Restart Plasma or KWin

KDE does not overwrite files inside ~/.local/share unless a theme with the same name is installed via Discover or package manager, so maintaining the name Noctis-round-Custom is recommended.

🔄 Uninstalling the Custom Theme
bash
Copiar código
rm -rf ~/.local/share/plasma/desktoptheme/Noctis-round-Custom
