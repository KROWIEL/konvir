# Third-party software

Konvir includes code and components from the projects listed below. Each component keeps its own
license, and the notices below are reproduced as required by those licenses.

## Sweetch

Parts of Konvir are derived from [Sweetch](https://github.com/krllmrzv/Sweetch), which is
distributed under the MIT License. The MIT License permits modification, relicensing and commercial
distribution, provided the notice below is retained.

```
MIT License

Copyright (c) 2026 Metamorfolog
Copyright (c) 2026 mmmorozov (Sweetch modifications)

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

## Lucide

The wheel icons are outlines from [Lucide](https://github.com/lucide-icons/lucide), converted to
path data in `src/Konvir.App/UI/IconPaths.cs` by `tools/generate-icons.ps1`. Lucide is distributed
under the ISC License, which permits commercial use provided the notice below is retained.

```
ISC License

Copyright (c) for portions of Lucide are held by Cole Bemis 2013-2022 as part of Feather (MIT).
All other copyright (c) for Lucide are held by Lucide Contributors 2022.

Permission to use, copy, modify, and/or distribute this software for any
purpose with or without fee is hereby granted, provided that the above
copyright notice and this permission notice appear in all copies.

THE SOFTWARE IS PROVIDED "AS IS" AND THE AUTHOR DISCLAIMS ALL WARRANTIES WITH
REGARD TO THIS SOFTWARE INCLUDING ALL IMPLIED WARRANTIES OF MERCHANTABILITY
AND FITNESS. IN NO EVENT SHALL THE AUTHOR BE LIABLE FOR ANY SPECIAL, DIRECT,
INDIRECT, OR CONSEQUENTIAL DAMAGES OR ANY DAMAGES WHATSOEVER RESULTING FROM
LOSS OF USE, DATA OR PROFITS, WHETHER IN AN ACTION OF CONTRACT, NEGLIGENCE OR
OTHER TORTIOUS ACTION, ARISING OUT OF OR IN CONNECTION WITH THE USE OR
PERFORMANCE OF THIS SOFTWARE.
```

## Bundled libraries

| Component | Used for | License |
|---|---|---|
| [Avalonia](https://github.com/AvaloniaUI/Avalonia) | User interface | MIT |
| [Magick.NET](https://github.com/dlemstra/Magick.NET) / ImageMagick | Images | Apache-2.0 / ImageMagick License |
| [PDFtoImage](https://github.com/sungaila/PDFtoImage) / PDFium / SkiaSharp | PDF to images | MIT / BSD-3-Clause / MIT |
| [PdfPig](https://github.com/UglyToad/PdfPig) | PDF text | Apache-2.0 |
| [PDFsharp](https://github.com/empira/PDFsharp) | Merge, split, rotate PDF | MIT |
| [ClosedXML](https://github.com/ClosedXML/ClosedXML) | XLSX | MIT |
| [ExcelDataReader](https://github.com/ExcelDataReader/ExcelDataReader) | XLS | MIT |
| [SharpCompress](https://github.com/adamhathcock/sharpcompress) | RAR, 7z, TAR and other archives | MIT |
| [Velopack](https://github.com/velopack/velopack) | Installer and updates | MIT |

## External programs

The components below are **not distributed with Konvir**. They are downloaded or installed by the
user onto the user's own machine, and Konvir invokes them as separate programs through their
command-line interfaces. Konvir does not link against them.

| Component | Used for | License |
|---|---|---|
| [FFmpeg](https://ffmpeg.org) | Audio and video | LGPL-2.1-or-later, or GPL depending on the build the user installs |
| [Pandoc](https://pandoc.org) | Documents | GPL-2.0-or-later |
| [LibreOffice](https://www.libreoffice.org) | Office files to PDF | MPL-2.0 |

This separation is deliberate and must be preserved: bundling these programs into the distribution,
or linking against their libraries, changes the licensing obligations substantially. See
`docs/PLAN.md` for details.
