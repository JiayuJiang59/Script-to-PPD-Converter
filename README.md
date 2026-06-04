# Script → PPD Converter

A browser-based tool that converts a color-coded Word script (`.docx`) into a
formatted PPD (Post-Production Document) table — also a `.docx`. It removes the
slow manual copy-and-paste of script content into the correct PPD columns.

Everything runs **entirely in your browser**. Uploaded files never leave your
device — there is no server and no upload.

## Live tool

👉 [Access to the Script to PPD Converter](https://jiayujiang59.github.io/Script-to-PPD-Converter/)

## What it does

You write a script in Word using a simple color code. The tool reads the text
**color** of each part and routes it into the right PPD column, preserving your
formatting exactly.

| In the script (text color) | Goes to PPD column | Notes |
|---|---|---|
| **Black** | Script | Spoken word, copied verbatim |
| **Green** | Graphics | On-screen text / graphics / exercises |
| **Red** | Video | Production note (kept with a "Prof.'s Production Notes:" label) |
| **Blue** | PlayPosit | Quiz / interactive content |

### It also handles

- **No text is ever changed** — wording is copied exactly.
- **Formatting carried over:** font, size, bold, italic, underline (and style),
  strikethrough, superscript/subscript, and text alignment (including centered).
- **Lists kept intact** — numbered (`1. 2. 3.`), lettered (`a. b. c.`) and
  bullets keep their markers, in their original color.
- **Consecutive same-color blocks** are merged into a single cell instead of
  being split across many rows.
- **Yellow highlight** is removed in the Script column but kept in Graphics and
  PlayPosit.
- **Modules and weeks auto-detected** from `Module #X` and `Week #X` headers.
- **Course code and week auto-detected** from the script's title line (editable).
- **Landscape output** with the standard four columns: Videos · Graphics ·
  Script · PlayPosit.

## How to use

1. Open the live tool (link above).
2. (Optional) Enter or confirm the course code and week — the tool tries to
   auto-fill these from your script.
3. Choose where green text should go (Graphics only, or Graphics + Script).
4. Upload your color-coded `.docx` script.
5. Review the on-screen preview, then click **Convert & Download .docx**.
6. Fill in the header rows (Team / ID / VP …) in the downloaded file.

## Writing a script

Download the included template, `Script_Template_ColorCoded.docx`, which has the
correct colors set up and an example for each one. Write your script using:

- **Black** for spoken narration
- **Green** for on-screen text, graphics, and exercises
- **Red** for production notes
- **Blue** for PlayPosit content (add yellow highlight where you want it kept)

Start each module with a heading like `Module #1:  Title`, and include a
`Week #__` line so the tool can detect the week.

## Running it yourself

No build step. It's a single HTML file using two libraries loaded from a CDN
(JSZip to read the `.docx`, docx.js to write the new one).

To run locally, just open `index.html` in a browser — or serve the folder with
any static server.

## Privacy

This tool does not upload, store, or transmit your files. All parsing and
document generation happen locally in your browser.

## License

Released under the MIT License. See [LICENSE](LICENSE).
