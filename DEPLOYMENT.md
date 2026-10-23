# Install and publish with GitHub Pages

Dastyar Plus is a static website. It does not require Node.js, package installation, a database, or an application server. Put the project files in a GitHub repository and use GitHub Pages to publish them.

[فارسی](DEPLOYMENT.fa.md) · [Back to the English README](README.md)

## What you need

- A GitHub account.
- The project files. After extracting the ZIP, work in the directory that directly contains `index.html` and the `css/` and `js/` folders.
- Git installed on your computer for the command-line method. You can also upload files through GitHub's website.

## 1. Run and check the site locally

From a terminal, change to the project root and start a small local web server:

```bash
cd path/to/dastyar-plus
python3 -m http.server 8000
```

Open <http://localhost:8000>. Press `Ctrl+C` in the terminal to stop the server. Opening `index.html` directly may also work, but serving it over HTTP is a better way to check the site.

Before publishing, check at least the following:

- Switch the interface to English and Persian. Confirm that English is left-to-right and Persian is right-to-left.
- Try the navigation, forms, tasks, notes, and timer on both desktop and mobile screen sizes.
- Do not add personal information, real photos, exported JSON backups, passwords, API keys, or other secrets to the repository.

## 2. Create a GitHub repository

On GitHub, choose **New repository** and pick a short, suitable repository name. Make the repository **Public** if you want anyone to access the website. The project already includes its README, license, and ignore file, so leave the options to add a README, license, or `.gitignore` unchecked to avoid conflicts.

## 3. Push the project with Git

Run these commands from the project root—the directory containing `index.html`. Replace `USERNAME` and `REPOSITORY` with your GitHub account and repository names:

```bash
git init
git add .
git commit -m "Prepare Dastyar Plus for GitHub Pages"
git branch -M main
git remote add origin https://github.com/USERNAME/REPOSITORY.git
git push -u origin main
```

If Git asks for a commit name and email, set your Git identity. For example:

```bash
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
```

The name and email may appear in commit history. You can use GitHub's private email address if you prefer. Never put your GitHub password or access token in project files or commits.

### Alternative: upload through the browser

In your repository on GitHub, choose **Add file → Upload files**, select the contents of the project folder, and commit them to the `main` branch. Do not upload the parent folder in a way that nests the whole project one directory too deep: `index.html` must be at the repository root.

## 4. Enable GitHub Pages

1. In the repository, open **Settings → Pages**.
2. Under **Build and deployment**, select **Deploy from a branch**.
3. Choose the `main` branch and the `/(root)` folder, then click **Save**.
4. Wait a few minutes. The deployment status appears on that page and usually under **Actions** as well.
5. The project URL is normally:

   ```text
   https://USERNAME.github.io/REPOSITORY/
   ```

   If the repository is named exactly `USERNAME.github.io`, the account site URL is `https://USERNAME.github.io/`.

Public repositories can be used for public sites. Publishing Pages from a private repository depends on your GitHub plan and settings. If the Pages option is unavailable, check GitHub's current documentation and plan limits.

## 5. Update the site

After editing files, run these commands from the project root:

```bash
git add .
git commit -m "Describe your update"
git push
```

GitHub Pages serves the new version after deployment completes. You may need to do a full page reload to see the latest changes.

## Data and privacy notes

- Profile details and dashboard content are stored in `localStorage` in the current browser. They are not uploaded to the GitHub repository and do not sync to another device.
- Information a visitor enters in the app is not normally written to the website files or repository. However, exported JSON backups are private data; do not commit or publicly upload them.
- Before clearing browser data or moving to another device, use **Settings → Data → Export** in the app and keep the backup somewhere safe.
- Fonts, icons, and the optional Monaco editor may load from third-party CDNs and require an internet connection. Some visual details or the optional editor may not load offline.

## Quick troubleshooting

- **404 page:** Confirm that Pages is configured for the `main` branch and `/(root)`, and that `index.html` is at the repository root.
- **CSS or JavaScript does not load:** Check the spelling and capitalization of `css/style.css` and `js/app.js`. GitHub Pages paths are case-sensitive.
- **Changes are not visible:** Check the deployment under **Settings → Pages** or **Actions**, then do a full page reload.
- **The dashboard is empty on another device:** This is expected because data is stored locally. Export a JSON backup from the old device and import it on the new one.

## License

This project is distributed under the MIT License. See [LICENSE](LICENSE) for details.
