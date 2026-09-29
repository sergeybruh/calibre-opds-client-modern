# Calibre OPDS Client for Python 3 and Qt 6

A maintained Calibre plugin for browsing OPDS catalogs and downloading ebooks directly into a Calibre library.

This project modernizes the original **Calibre OPDS Client** for current Calibre releases. It replaces obsolete Python 2 networking APIs and updates the user interface for Calibre's Qt 6 runtime.

## Features

- Add and remember custom OPDS catalog URLs.
- Browse OPDS 1.x navigation and acquisition feeds.
- Search and filter catalog results.
- Download selected ebooks into the current Calibre library.
- Hide newspapers or books already present in the library.
- Connect to Calibre Content Server, Calibre-Web, Project Gutenberg, and other compatible OPDS services.
- Run on macOS, Windows, and Linux with Calibre 6 or newer.

Use the plugin only with catalogs and publications you are authorized to access.

## Compatibility

- Calibre 6.0 or newer
- Python 3 runtime bundled with Calibre
- Qt 6 runtime bundled with Calibre
- macOS, Windows, or Linux

Version 1.1.0 was tested with Calibre 6.3 on Apple Silicon macOS. Reports and pull requests for newer Calibre versions and other platforms are welcome.

## Installation

1. Download `OPDS-Client-v1.1.0.zip` from the latest GitHub release. Do not extract it.
2. Open Calibre.
3. Select **Preferences → Plugins → Load plugin from file**.
4. Choose the downloaded ZIP file and approve the third-party plugin warning.
5. Restart Calibre.
6. Open **Preferences → Toolbars & menus**.
7. Choose **The main toolbar**.
8. Select **OPDS Client** under **Available actions** and add it to **Current actions**.
9. Select **Apply**, then **Close**.

To display the button while an ereader is connected, repeat the toolbar steps for **The main toolbar when a device is connected**.

## Quick test with Project Gutenberg

Project Gutenberg publishes a legal public-domain OPDS catalog.

1. Open **OPDS Client** from the Calibre toolbar.
2. Enter this URL and press Return:

   ```text
   https://www.gutenberg.org/ebooks/search.opds/
   ```

3. Choose an item under **OPDS Catalog**.
4. Select **Download OPDS**.
5. Select a book and choose **Download selected books**.

## Install from source

Clone the repository and run Calibre's plugin builder from the plugin directory:

```bash
git clone https://github.com/sergeybruh/calibre-opds-client-modern.git
cd calibre-opds-client-modern/calibre_plugin
calibre-customize -b .
```

On macOS, if `calibre-customize` is not in your shell path:

```bash
/Applications/calibre.app/Contents/MacOS/calibre-customize -b .
```

Restart Calibre after installation.

## What changed from the original

Version 1.1.0 adds compatibility with modern Calibre runtimes:

- Replaced the removed Python 2 `urllib2` and `urlparse` modules with Python 3 equivalents.
- Replaced obsolete Qt enum access with Qt 6 scoped enums.
- Replaced legacy `PyQt5` imports with Calibre's supported `qt.core` compatibility layer.
- Raised the minimum supported Calibre version to 6.0.

## Development

Run formatting and lint checks with:

```bash
python3 -m pip install tox
tox -e black-check,flake8
```

Build and install locally with:

```bash
cd calibre_plugin
calibre-customize -b .
```

## History and attribution

This project is based on work by Steinar Bang and the `goodlibs/calibre-opds-client` fork. The original copyright notices remain in the source files and the Git history is preserved.

## License

Licensed under the [GNU General Public License v3.0](LICENSE). Modified versions must remain available under the same license when distributed.

## Search keywords

Calibre OPDS client, Calibre plugin, OPDS catalog browser, ebook downloader, EPUB library, Calibre-Web, Calibre Content Server, Python 3, Qt 6, macOS ebook reader, Windows ebook manager, Linux ebook library.
