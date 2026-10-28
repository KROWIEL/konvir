<div align="center">

# Konvir

**A file converter that lives on a radial menu.**
Select files, press the shortcut, pick a slice.

English · [Русский](README.ru.md)

<img src="docs/images/wheel-convert.png" width="420" alt="The convert wheel over a selected image">

</div>

Images, audio, video, PDF, documents, spreadsheets, slides, subtitles and archives. Everything
runs on your machine — no file is ever uploaded anywhere.

## How it works

1. Select files in Explorer or on the desktop.
2. Press `Ctrl+Alt+Space`. The wheel opens under the cursor, showing only what fits the selection.
3. Click a slice. Progress appears in a small panel in the corner, and the result lands next to
   the original or in a folder you chose. The panel leaves five seconds after the last job, green
   or red, draining a bar so you can see it going.

With nothing selected the wheel opens empty, as a target: drop files on it and it fills in.

## Three wheels

`Tab` or the scroll wheel switches between them. A wheel with nothing to offer is never shown, so
every slice you can reach does something.

Right-click a slice to move it to the front of its wheel or take it off entirely. The wheel is
its own settings screen for this: the slice you want gone is the one already under the pointer.
Hidden slices are listed in the settings, where they can be put back.

| Convert | Tools | Actions |
|:--:|:--:|:--:|
| <img src="docs/images/wheel-convert.png" width="260" alt="Convert wheel"> | <img src="docs/images/wheel-tools.png" width="260" alt="Tools wheel"> | <img src="docs/images/wheel-actions.png" width="260" alt="Actions wheel"> |
| One format into another | Compress, resize, rotate, strip metadata, archive | Copy path, copy name, open a terminal, SHA-256 |

## Your own slices

A preset is a conversion you describe once and then reach from the wheel: "Web 1920" as JPEG at
quality 82 with the metadata stripped, or "Podcast" as 128 kbit/s MP3. Build them in the settings;
each becomes a slice of its own, named by you.

A preset that changes the format lands on the convert wheel. One that keeps the format — half
size, grayscale, metadata removed — lands on tools, because it edits the file rather than turning
it into something else. Results are named after the preset: `photo (Web 1920).jpg`.

## Formats

| Kind | In | Out |
|---|---|---|
| Images | JPG, PNG, WEBP, HEIC, TIFF, AVIF, BMP, GIF, SVG, ICO and 25 raw formats | JPG, PNG, WEBP, AVIF, TIFF, ICO, PDF |
| Audio | MP3, M4A, AAC, WAV, FLAC, OGG, OPUS, AIFF, WMA | MP3, M4A, WAV, FLAC, OGG, OPUS, AIFF |
| Video | MP4, MOV, MKV, WEBM, AVI, WMV, FLV, MPG, 3GP, TS | MP4, MOV, MKV, WEBM, GIF, MP3 |
| Documents | DOCX, DOC, ODT, RTF, MD, TXT, HTML, EPUB | DOCX, PDF, ODT, MD, HTML, TXT, EPUB, RTF |
| Spreadsheets | XLSX, XLSM, XLS, ODS, CSV, TSV | XLSX, CSV, TSV, ODS, PDF |
| Slides | PPTX, PPT, ODP | PDF, PNG, JPG, PPTX, ODP |
| Subtitles | SRT, VTT | SRT, VTT, TXT |
| Archives | ZIP, TAR, GZ, BZ2, XZ, RAR, 7Z | ZIP, TAR, TAR.GZ |
| PDF | PDF | PNG, JPG, DOCX, TXT, MD, HTML, EPUB |

## Settings

<div align="center">
<img src="docs/images/settings.png" width="420" alt="The settings window">
</div>

Six tabs: general, the wheel's own slices, the quality knobs each conversion uses, the external
programs, the watched folders, and your licence. Changes take effect as you make them — there is
no OK button to forget.

Konvir follows the system between its light and dark colours, and the general tab can pin it to
one of them.

To change the shortcut, click it and press the combination you want. Anything with at least one
modifier is accepted; if another program already owns it, the window says so instead of leaving
you with a shortcut that does nothing.

## External programs

Media and office conversions are done by three well-known programs, and Konvir runs them as
separate command-line processes:

| Program | Needed for | How to get it |
|---|---|---|
| FFmpeg | Audio and video | The **Install** button downloads it, checksum verified |
| Pandoc | Documents and e-books | The **Install** button: through winget on Windows, downloaded and checksum verified on macOS |
| LibreOffice | DOCX, XLSX, PPTX and ODF | Windows: the **Install** button, through winget. macOS: **Download…** opens libreoffice.org |

Konvir never ships these programs: you install them, on your machine, from their own publishers.
That separation is deliberate and is kept on purpose: their licences stay with them.

Everything else — images, PDF, spreadsheets, subtitles, archives — works with nothing installed.

## Installing

Windows builds are published on the
[Releases page](https://github.com/KROWIEL/konvir/releases): an installer and a portable archive.
The installer puts Konvir in `%LOCALAPPDATA%\Konvir` and can start it with the computer; Konvir
checks for newer versions on its own and installs them when you next close it.

Or through the Windows Package Manager, which checks the download against its own checksum:

```
winget install Konvir.Konvir
```

### About the SmartScreen warning

Downloading the installer yourself gets you "Windows protected your PC". Choose **More info**
and then **Run anyway**.

Konvir is not signed with a code signing certificate yet. We would rather say that plainly than
have you wonder: a certificate costs a few hundred dollars a year, and — this is the part nobody
mentions — it would not remove the warning either. SmartScreen shows it for signed installers
too, until a file has been downloaded enough times to have a history. What signing buys is that
the history carries from one release to the next instead of starting over every time, which is
worth paying for once there are enough downloads for it to mean anything.

Until then: every release lists the SHA-256 of each file, so you can check that what you
downloaded is what we built.

```powershell
Get-FileHash .\Konvir-win-Setup.exe -Algorithm SHA256
```

### macOS

macOS 13 or later on Apple Silicon (M1 and newer). The same page has an installer,
`Konvir-osx-Setup.pkg`, and a portable archive. Konvir sits in the menu bar rather than the Dock,
and the shortcut is ⇧⌘Space.

Konvir is not notarised by Apple yet, so macOS refuses to open it the first time. Open
**System Settings → Privacy & Security** and choose **Open Anyway**. The first time you open the
wheel on files selected in Finder, macOS also asks whether Konvir may control Finder: that is how
it learns which files are selected. Installed for all users, Konvir asks for an administrator
password once, at its first update.

```sh
shasum -a 256 Konvir-osx-Setup.pkg
```

## Platform support

| | Shortcut | Tray | File manager selection |
|---|:--:|:--:|:--:|
| Windows 10/11 | yes | yes | Explorer |
| macOS 13+ | yes | menu bar | Finder |
| Linux | planned | planned | planned |

The conversion core and the interface are already cross-platform; what Linux is missing is the
native layer.

## Buying

Konvir converts everything for 14 days, with nothing to sign up for. After that it needs a key.

A key is issued for one computer. **Settings → Licence** shows that computer's device code —
send it with your order, and the key that comes back goes in the same place along with the
address you bought it with. The key does not expire.

Keys are checked on your own machine, so Konvir works offline and keeps working if this site
ever goes away. Nothing about your computer is sent anywhere: the device code is a hash, and
what it was made from never leaves the machine.

## Licence

Konvir is proprietary software. Its conversion core began as a fork of
[krllmrzv/Sweetch](https://github.com/krllmrzv/Sweetch) (MIT); the required copyright notices and
every dependency's licence are kept in [`LICENSE`](LICENSE) and
[`THIRD-PARTY-NOTICES.md`](THIRD-PARTY-NOTICES.md).
