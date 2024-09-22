# medium-publish

## Overview

**Medium Publish** is a Python package designed to streamline the process of converting Markdown files into HTML, while also enabling the embedding of images and publishing code snippets as Gists on GitHub. This tool is particularly useful for writers and developers who want to share their content on Medium with rich formatting and embedded resources.

## Features

- **Markdown Processing**: Convert Markdown files to HTML with support for code blocks and lists.
- **Image Handling**: Automatically embed images from URLs or local paths into the generated HTML.
- **Gist Publishing**: Publish code snippets as Gists on GitHub and replace them in the HTML with links.
- **Clipboard Support**: Copy the final HTML output directly to your clipboard for easy sharing.

## Table of Contents

- [Installation](#installation)
- [Usage](#usage)
- [File Structure](#file-structure)
- [Configuration](#configuration)
- [Contributing](#contributing)
- [License](#license)

## Installation

To install Medium Publish, you need to have Python 3.12 or higher. You can install the package using Poetry:

```bash
poetry install
```

## Usage

To use Medium Publish, run the command line interface (CLI) tool with the required parameters:

```bash
medium-publish <file_path> [--output <output_path>] [--embed-images]
```

### Parameters

- `file_path`: The path to the Markdown file you want to process.
- `--output`: (Optional) Specify an output file path for the modified HTML.
- `--embed-images`: (Optional) Use this flag to embed images in the output HTML.

### Example

```bash
medium-publish my_article.md --output my_article.html --embed-images
```

This command will process `my_article.md`, embed any images found, and save the output as `my_article.html`.

## File Structure

The project is organized as follows:

```
medium_publish/
├── __init__.py          # Package initialization
├── image_processor.py    # Image downloading and embedding logic
├── process_file.py       # Markdown processing functions
├── copy_to_clipboard.py  # Functionality to copy HTML to clipboard
├── main.py               # Main entry point for CLI tool
└── .gitignore            # Git ignore file
pyproject.toml            # Project metadata and dependencies
README.md                 # Project documentation
```

## Configuration

Before running Medium Publish, ensure you have set your GitHub token in your environment variables:

```bash
export GITHUB_TOKEN="your_github_token"
```

This token is required for publishing Gists.

## Contributing

Contributions are welcome! If you have suggestions or improvements, please fork the repository and submit a pull request. 

1. Fork it (https://github.com/yourusername/medium-publish/fork)
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a pull request

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
