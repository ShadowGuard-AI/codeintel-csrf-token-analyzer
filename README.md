![The token pouch changing hands close up, the signalman's hand passing the open leather pouch with its plain brass token to the driver's gloved hand at the train cab](intro-banner.png)

# codeintel-CSRF-Token-Analyzer

![A country station platform at dusk where the signalman hands the brass token in its leather pouch to the driver at the cab window, a single line of rail running away into flat fields](banner.png)

![One round brass token with a plain scratched face resting in its open leather pouch on a station bench, the pouch stitching clear](logo.png)

![The lane at dusk in three depths: the sky deepening by slow degrees with stars pricking through one by one, the emperor moth in slow heavy flight in a wide loop around the lamp with ant trails filing below it, and dew gathering on a web between two grass stems, one bead forming, swelling, and holding](scene.svg)


Verifies the implementation of CSRF protection mechanisms in web application code, focusing on token generation and validation. Focused on tools for static code analysis, vulnerability scanning, and code quality assurance.

![Major separator: a spider web line running the full rule with dew beads forming along its length from left to right, silver on moth taupe](sep-heavy.svg)

## Install
`git clone https://github.com/ShadowGuard-AI/codeintel-csrf-token-analyzer`

![Minor separator: one centred dew bead on a spider web line with plain rule on either side, silver on moth taupe](sep-light.svg)

## Usage
`python3 main.py SOURCE_CODE_PATH [--token_name NAME] [--form_field FIELD] [--exclude PATH ...]`

![Major separator: a spider web line running the full rule with dew beads forming along its length from left to right, silver on moth taupe](sep-heavy.svg)

## Parameters
- `-h`: Show help message and exit
- `source_code_path`: Path to the source code directory or file. Required.
- `--token_name`: Name of the CSRF token (default: csrf_token).
- `--form_field`: Name of the CSRF form field (default: csrf_token).
- `--exclude`: List of files or directories to exclude.

> **Collector's note: the identifier rule.** The token name and the form field must each be a plain identifier, a letter or underscore followed by letters, digits, or underscores, because both names are placed into the search patterns as raw pattern text. A run with any other shape of name is refused with an error and exit 1.

![Major separator: a spider web line running the full rule with dew beads forming along its length from left to right, silver on moth taupe](sep-heavy.svg)

## Verified behavior
- A Python file containing a token generation call and a form-field comparison against the token reports both generation and validation logic found.
- A file with neither reports both as not found, and still exits 0. The exit code does not distinguish a clean file from a file with no CSRF logic, so read the log lines, not the exit code, for the result.

> **Collector's note: found across the tree is not found in one file.** A directory run pools its two findings across the whole tree, so generation in one file and validation in another reads as both present even when no single file does both halves.

> **Collector's note: exit 0 proves nothing either way.** The exit code does not distinguish a clean file from a file with no CSRF logic. Read the log lines, not the exit code, for the result.

> **Collector's note: Python files only.** Only files ending in .py are read, so token handling written in any other language or in a template is outside the check altogether.

![Major separator: a spider web line running the full rule with dew beads forming along its length from left to right, silver on moth taupe](sep-heavy.svg)

## License
See LICENSE.
