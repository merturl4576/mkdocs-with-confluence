# MyFile Documentation Project

This project uses MkDocs to generate documentation locally and integrates with Atlassian Confluence to automatically publish pages.

## Installation

1. **Clone the repository**

   ```bash
   git clone https://github.com/ITSDeniz/mkdocs-with-confluence.git
   cd mkdocs-with-confluence
   ```

2. **Create and activate a virtual environment**

   ```bash
   python -m venv .venv
   # PowerShell
   .\.venv\Scripts\Activate.ps1
   # macOS/Linux
   source .venv/bin/activate
   ```

3. **Install dependencies**

   ```bash
   pip install --upgrade pip
  	pip install mkdocs mkdocs-material mkdocs-with-confluence
   pip install -r requirements.txt
   ```

4. **Set environment variable for Confluence publishing**

   ```powershell
   $env:MKDOCS_TO_CONFLUENCE = "1"
   ```

   (For macOS/Linux: `export MKDOCS_TO_CONFLUENCE=1`)

## Usage

* **Local preview:**

  ```bash
  mkdocs serve
  ```

  Opens a development server at `http://127.0.0.1:8000/`.

* **Build static site:**

  ```bash
  mkdocs build
  ```

  Generates the `site/` folder with static HTML files.

* **Publish to Confluence:**

  ```bash
  mkdocs build -v
  ```

  Publishes or updates pages under the configured parent in Confluence.

## Configuration

Edit `mkdocs.yml` to set your Confluence credentials and parent page:

```yaml
plugins:
  - mkdocs-with-confluence:
      host_url: "https://your-domain.atlassian.net/wiki/rest/api/content"
      space: "<SPACE_KEY>"
      parent_page_name: "Overview"
      username: "you@domain.com"
      password: "<API_TOKEN>"
```

## GitHub Pages Deployment (Optional)

```bash
mkdocs gh-deploy --clean
```

Publishes the static site to GitHub Pages at `https://your-username.github.io/your-repo/`.

## License

MIT © ITSDeniz
