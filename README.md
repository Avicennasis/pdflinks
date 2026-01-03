# pdflinks

A modern command-line tool to extract PDF links from webpages.

![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)
![Bash](https://img.shields.io/badge/Bash-4.0%2B-green.svg)

## Features

- 🔍 **Extract PDF links** from any webpage
- 📥 **Optional download** of all found PDFs
- 🎨 **Colored output** for better readability
- 🔗 **Handles relative URLs** automatically
- 📝 **Saves links** to a text file
- ⚡ **Fast** - uses curl for efficient fetching

## Requirements

The following standard Unix utilities are required (pre-installed on most systems):

- `curl` - for fetching webpages
- `grep` - for pattern matching
- `sed` - for text processing
- `bash` 4.0+

## Installation

```bash
# Clone the repository
git clone https://github.com/Avicennasis/pdflinks.git

# Make the script executable
chmod +x pdflinks/pdflinks.sh

# Optionally, add to your PATH
sudo ln -s $(pwd)/pdflinks/pdflinks.sh /usr/local/bin/pdflinks
```

## Usage

```bash
# Basic usage - extract PDF links from a webpage
./pdflinks.sh https://example.com/documents

# Save links to a custom file
./pdflinks.sh -o my_links.txt https://example.com/papers

# Extract and download all PDFs
./pdflinks.sh --download https://example.com/reports

# Download to a specific directory
./pdflinks.sh -d -D ./my_pdfs https://example.com/files

# Quiet mode (only show links and errors)
./pdflinks.sh -q https://example.com/docs
```

## Options

| Option | Description |
|--------|-------------|
| `-h, --help` | Show help message and exit |
| `-v, --version` | Show version information |
| `-d, --download` | Download all found PDF files |
| `-o, --output FILE` | Save links to FILE (default: `pdflinks.txt`) |
| `-D, --dir DIR` | Download directory (default: `pdf_downloads`) |
| `-q, --quiet` | Suppress informational output |

## Example Output

```
[INFO] Fetching PDF links from: https://example.com/documents
[OK] Found 5 PDF link(s)

PDF Links:
----------------------------------------
https://example.com/documents/report-2026.pdf
https://example.com/documents/whitepaper.pdf
https://example.com/documents/guide.pdf
https://example.com/documents/manual.pdf
https://example.com/documents/specs.pdf
----------------------------------------

[INFO] Links saved to: pdflinks.txt
[OK] Done!
```

## History

- **v2.0.0** (2026) - Complete rewrite by Léon "Avic" Simmons
  - Replaced lynx with curl
  - Added colored output and progress indicators
  - Added download functionality with `--download` flag
  - Added help system and version info
  - Improved error handling and URL validation
  - Extensive code documentation

- **v1.0.0** (2013) - Original version by [Glutanimate](http://askubuntu.com/users/81372/)

## License

MIT License - see [LICENSE](LICENSE) for details.

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.
