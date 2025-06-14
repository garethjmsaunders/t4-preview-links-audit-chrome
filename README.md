# T4 Preview Link Auditor Chrome extension

## Description

This tool audits all links within the

* `<main id="content-begin">` (T4 New) or
* `<div id="mainwrapper">` (T4 Old)

sections of T4 preview (or live) pages. It categorises, highlights and logs them when you click the extension button.

## How to install

1. **Download**: Download the extension zip file.
2. **Unzip**: Extract the contents of the zip file to a folder on your computer.
3. **Open Chrome Extensions**: In Google Chrome, go to chrome://extensions/.
4. **Enable Developer Mode**: Use the toggle in the top right corner to turn on Developer Mode.
5. **Load Unpacked**: Click Load unpacked and select the folder where you unzipped the extension.
6. The T4 Preview Link Auditor button should now appear in your Chrome toolbar. (You may need to click the Extensions button to locate it and pin it to your toolbar.)

## How to Use

1. Navigate to a preview page in T4.
2. Click the T4 Preview Link Auditor icon in the Chrome toolbarExtension icon.
3. All links within the main content will be highlighted using the colour categories below.
4. Open the Developer Console (F12 → Console tab) to view the audit results.
5. To reset the page and remove colour highlights, simply refresh the current page.

## Link categories and highlight colours

* BLUE: St Andrews links – Links to `*.st-andrews.ac.uk` (excluding t4live).
* RED: T4 links – Links to other pages in T4 preview (e.g. https://t4live.st-andrews.ac.uk/...).
* YELLOW: External links – Links to domains outside st-andrews.ac.uk, including valid mailto: and tel: addresses.
* BLACK: Relative links – Links using relative paths (e.g. /students/).
* BLACK: Anchor links – Links starting with # that point to on-page IDs.
* ORANGE: Malformed tel: links – Telephone links containing spaces or %20.

## Supported file types

The extension automatically adds a filetype icon after links ending with these extensions:

* .doc
* .docx
* .pdf
* .xls
* .xlsx
* .ppt
* .pptx
* .zip

Links to these file types are styled according to their domain: St Andrews (blue) or external (yellow).

## Extra highlighting

* Email: mailto: @st-andrews.ac.uk → St Andrews (blue)
* Email: mailto: @ any other domain → External (yellow)
* Phone: tel: links → External (yellow) with telephone icon
* Phone: tel: links with spaces or %20 → Highlighted in orange with telephone icon

## Console output

After activation, links are listed in the Console grouped by category and in order of appearance. Each link includes its text and full URL.
