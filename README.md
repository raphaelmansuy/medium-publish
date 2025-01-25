# medium-publish

## Overview

**Medium Publish** is a Python package designed to streamline the process of converting Markdown files into HTML, while also enabling the embedding of images and publishing code snippets as Gists on GitHub. This tool is particularly useful for writers and developers who want to share their content on Medium with rich formatting and embedded resources. It simplifies the workflow for publishing technical articles, ensuring seamless integration of code and visuals.

## Features

- **Markdown Processing**: Convert Markdown files to HTML with support for code blocks, lists, and other formatting elements, ensuring compatibility with Medium's editor.
- **Gist Publishing**: Automatically publish code snippets as Gists on GitHub and replace them in the HTML with links, making your code snippets interactive and shareable.
- **Image Handling**: Embed images from URLs or local paths directly into the generated HTML, eliminating the need for manual image uploads.
- **Clipboard Support**: Copy the final HTML output directly to your clipboard for quick and easy pasting into Medium or other platforms.

## Table of Contents

- [Installation](#installation)
- [Usage](#usage)
- [File Structure](#file-structure)
- [Configuration](#configuration)
- [Contributing](#contributing)
- [License](#license)

## Installation

To install Medium Publish, you need to have Python 3.12 or higher. The recommended way to install the package is using Poetry:

```bash
poetry install
```

Alternatively, you can install it using `pip`:

```bash
pip install medium-publish
```

## Usage

Medium Publish provides a command-line interface (CLI) to process Markdown files and generate HTML output. Before running the tool, ensure you have set your GitHub token in your environment variables (see [Configuration](#configuration)).

To use Medium Publish, run the CLI tool with the required parameters:

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
├── image_processor.py    # Handles image downloading and embedding logic
├── process_file.py       # Contains functions for Markdown processing
├── copy_to_clipboard.py  # Provides functionality to copy HTML to clipboard
├── main.py               # Main entry point for the CLI tool
└── .gitignore            # Specifies files and directories ignored by Git
pyproject.toml            # Defines project metadata and dependencies
README.md                 # Project documentation
```

## Configuration

### Environment Variables
Create a `.env` file in the root directory with the following variables:

```plaintext
GITHUB_TOKEN=XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
S3_FOLDER=s3://elitizon-public/assets/

```

Replace the placeholders with your actual credentials.

### AWS S3 Setup
The `medium-publish` CLI uses AWS S3 to store images referenced in your Markdown files. Ensure you have:
- An AWS account with S3 access.


The CLI will automatically upload images to the specified S3 bucket and replace local image paths with the corresponding S3 URLs in the published article.

### GitHub Token
Before running Medium Publish, ensure you have set your GitHub token in your environment variables. This token is required for publishing Gists.

```bash
export GITHUB_TOKEN="your_github_token"
```

To create a GitHub token, follow the [official GitHub documentation](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens).

This token is required for publishing Gists.

## Contributing

Contributions are welcome! If you have suggestions or improvements, please fork the repository and submit a pull request. 

1. Fork it (https://github.com/raphaelmansuy/medium-publish)
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a pull request

Please ensure your code follows the project's coding standards and includes appropriate tests.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.


## About the Author

**Raphaël MANSUY** is an AI/Data Engineering Architect and CTO at Elitizon, with over 20 years of experience scaling AI systems and data infrastructure for global enterprises and startups. A co-author of *The Definitive Guide to Data Integration* (Packt, 2024) and Oxford AI Tutor, he combines technical expertise with strategic impact to deliver scalable, future-proof solutions. 

Contact: raphael.mansuy_@_elitizon.com
