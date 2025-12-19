# Publishing Dark Glass Theme to Zed Extensions

This guide explains how to publish your Dark Glass Theme extension to the official Zed Extensions store.

## Prerequisites

1. A GitHub account
2. Your extension in a public GitHub repository
3. A valid LICENSE file (required as of October 1, 2025)

## Step-by-Step Publishing Process

### 1. Push Your Extension to GitHub

First, create a new repository on GitHub and push your extension:

```bash
# Create a new repo on GitHub first, then:
cd ~/git/dark-glass-theme

# Set up the remote (replace with your GitHub username)
git remote add origin https://github.com/YOUR_USERNAME/dark-glass-theme.git

# Create initial commit
git commit -m "Initial commit: Dark Glass Theme for Zed"

# Push to GitHub
git push -u origin main
```

### 2. Update extension.toml

Make sure to update the following fields in `extension.toml`:

```toml
authors = ["Your Name <your-email@example.com>"]
repository = "https://github.com/YOUR_USERNAME/dark-glass-theme"
```

### 3. Test Your Extension Locally

Before publishing, test your extension in Zed:

1. Open Zed
2. Press `cmd+shift+p` (or `ctrl+shift+p` on Linux/Windows)
3. Type "extensions" and select "zed: extensions"
4. Click "Install Dev Extension"
5. Navigate to `~/git/dark-glass-theme` and select it
6. Test the theme to make sure everything works

### 4. Publish to Zed Extensions

To publish your extension to the official Zed Extensions store:

1. **Fork the extensions repository**:
   - Go to https://github.com/zed-industries/extensions
   - Click "Fork" to create your own copy

2. **Add your extension as a submodule**:
   ```bash
   # Clone your fork
   git clone https://github.com/YOUR_USERNAME/extensions.git
   cd extensions

   # Add your extension as a submodule
   git submodule add https://github.com/YOUR_USERNAME/dark-glass-theme.git extensions/dark-glass-theme

   # Commit the changes
   git add .
   git commit -m "Add dark-glass-theme extension"
   git push
   ```

3. **Open a Pull Request**:
   - Go to your fork on GitHub
   - Click "Pull Request"
   - Create a PR to the main `zed-industries/extensions` repository
   - Title: "Add dark-glass-theme extension"
   - Description: Briefly describe your theme and its features

4. **Wait for Review**:
   - The Zed team will review your PR
   - CI checks will run automatically (including license validation)
   - Address any feedback if requested
   - Once approved and merged, your extension will be available in the Zed Extensions store!

## Updating Your Extension

When you want to release updates:

1. Make changes to your extension repository
2. Update the version in `extension.toml`
3. Commit and push to your repository
4. The changes will automatically appear in Zed (may take some time to propagate)

## Important Notes

- **License Required**: Your repository MUST include a LICENSE file at the root. Without it, the CI check will fail.
- **Version Format**: Use semantic versioning (e.g., "0.1.0", "1.0.0", "1.2.3")
- **Schema Version**: Keep `schema_version = 1` in your extension.toml
- **Repository URL**: Must be a valid, public GitHub repository

## Resources

- [Zed Extension Documentation](https://zed.dev/docs/extensions/developing-extensions)
- [Theme Extensions Guide](https://zed.dev/docs/extensions/themes)
- [Extensions Repository](https://github.com/zed-industries/extensions)
- [Zed Extensions Store](https://zed.dev/extensions)

## Support

If you encounter issues:
- Check the [Zed documentation](https://zed.dev/docs)
- Ask in the [Zed Discord](https://discord.gg/zed)
- Open an issue in the [Zed repository](https://github.com/zed-industries/zed)
