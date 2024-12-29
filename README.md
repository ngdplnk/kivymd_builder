# KivyMD App Builder Template with GitHub Actions

Welcome to the KivyMD App Builder Template! This repository provides a ready-to-use structure for building and deploying KivyMD applications, with integrated GitHub Actions for automation.

## Features

- **Pre-configured environment**: Start building your app right away.
- **GitHub Actions workflows**:
  - Automate building APKs for Android.
  - Streamline testing and deployment processes.
- **Modular and extensible**: Easily adapt the template to suit your needs.
- **MIT Licensed**: Use it freely for personal or commercial projects.

## Getting Started

### Prerequisites

Before using this template, ensure you have:
- [Python 3.12.8](https://www.python.org/downloads/release/python-3128/) (with functional `pip`)
- A Github account

### Using the Template

1. **Create a new repository** from this template:
   - Click on the "Use this template" button at the top of this repository.
   - Fill in your repository details and click "Create repository from template."

2. **Clone your new repository**:
   ```bash
   git clone https://github.com/your-username/your-repo-name.git
   cd your-repo-name
   ```

3. **Install dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

4. **Start developing**:
   - Edit the provided `main.py` to customize your app.
   - Add your KivyMD components and logic.

5. **Check the `buildozer.spec` file**:
   - Open the `buildozer.spec` file in the root directory.
   - Update the required fields such as `package.name`, `package.domain`, and `source.dir` to match your app's details.
        - Try not to modify the NDK version or you might have to adjust the workflow manually. The workflow works fine with things like that as they are in the template. Any changes you make will need to be made to ensure that the workflow works correctly.

6. **Push changes to GitHub**:
   ```bash
   git add .
   git commit -m "Initial commit"
   git push
   ```

### GitHub Actions Workflow

This template includes a pre-configured workflow to build APKs for Android:

1. Navigate to the `.github/workflows/` directory.
2. Review the `build.yml` file to customize the build process.
3. Push your changes to trigger the workflow.

### Configuring Permissions for GitHub Actions

If the workflow requires pushing changes to the repository:

1. **Set repository workflow permissions**:
   - Go to your repository on GitHub.
   - Navigate to **Settings** > **Actions** > **General**.
   - Scroll to the **Workflow permissions** section at the bottom.
   - Select **Read and write permissions** and save changes.

2. **(Optional) Create a Personal Access Token (PAT)** if additional authentication is needed:
   - Go to your [GitHub Developer Settings](https://github.com/settings/tokens).
   - Generate a new token with the necessary scope (`repo` for private repositories, `public_repo` for public ones).
   - Copy the token securely (it will only be displayed once).

3. **Add the PAT to your repository secrets**:
   - Navigate to your repository on GitHub.
   - Go to **Settings** > **Secrets and variables** > **Actions** > **New repository secret**.
   - Name it `GITHUB_TOKEN` and paste your PAT.

4. **Update the workflow to use the secret**:
   ```yaml
   env:
     GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
   ```

## File Structure

```
├── .github/
│   └── workflows/
│       └── build.yml       # GitHub Actions workflow for APK builds
├── assets/                 # Static assets for your app like images or fonts
|       └── icon.png        # Your APP icon (192x192px)
|       └── presplash.png   # Your APP presplash (1080x2400px recommended)
├── buildozer.spec          # Buildozer's details for your app
├── LICENSE                 # License file (MIT)
├── main.py                 # Main application file
├── README.md               # This readme
└── requirements.txt        # Python dependencies
```

## Contributing

Contributions are welcome! Feel free to open an issue or submit a pull request to improve this template.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Acknowledgments

- [Kivy](https://kivy.org/)
- [KivyMD](https://kivymd.readthedocs.io/)
- GitHub Actions for CI/CD automation
