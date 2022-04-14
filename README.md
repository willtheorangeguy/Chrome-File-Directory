<!-- Logo -->
<h1 align="center">
  <img src="https://raw.githubusercontent.com/willtheorangeguy/Chrome-File-Directory/main/docs/images/logo.png" height="250px" width="550px" alt="Chrome File Directory">
  <br>
  Chrome File Directory
  <br>
</h1>

<!-- Copy -->
<h4 align="center">The basic Chrome file directory page, as a simple HTML page.</h4>

<!-- Badges -->
<div align="center">
  <!-- Stability -->
  <img alt="GitHub Actions State" src="https://github.com/willtheorangeguy/Chrome-File-Directory/actions/workflows/pages/pages-build-deployment/badge.svg">
  <!-- Version -->
  <img alt="GitHub Version" src="https://img.shields.io/github/v/release/willtheorangeguy/Chrome-File-Directory">
  <!-- Issues -->
  <img alt="GitHub Issues" src="https://img.shields.io/github/issues/willtheorangeguy/Chrome-File-Directory">
  <!-- Pull Requests -->
  <img alt="GitHub Pull Requests" src="https://img.shields.io/github/issues-pr/willtheorangeguy/Chrome-File-Directory">
  <!-- Discord -->
  <img alt="Discord Server ID" src="https://img.shields.io/discord/962928406595514379">
  <!-- Downloads -->
  <img alt="Downloads" src="https://img.shields.io/github/downloads/willtheorangeguy/Chrome-File-Directory/total">
  <!-- Language Count -->
  <img alt="GitHub Languages" src="https://img.shields.io/github/languages/count/willtheorangeguy/Chrome-File-Directory">
</div>

<!-- Navigation -->
<p align="center">
  <a href="#key-features">Key Features</a> •
  <a href="#download">Download</a> •
  <a href="#how-to-use">How To Use</a> •
  <a href="#support">Support</a> •
  <a href="#contributing">Contributing</a> •
  <a href="#changelog">Changelog</a> •
  <a href="#credits">Credits & Contributors</a>
</p>

<!-- Screenshot(s) -->
![screenshot](https://raw.githubusercontent.com/willtheorangeguy/Chrome-File-Directory/main/docs/images/welcome.png)

## Key Features

* Basic file directory view.
* Name, type, size and upload date.
* Folder and file links.
* Icons for folders and files.
* Compatible with all web servers and websites.
* Includes an automatically generated file listing.
* Cross platform.

## Download

You can **[download](https://github.com/willtheorangeguy/Chrome-File-Directory/releases/latest) the source code** to modify the code and create your own file directory page.

You can also access the **production version the website**, available on all platforms, **[here](https://willtheorangeguy.github.io/Chrome-File-Directory/)**.

## How To Use

To clone and run this website, you'll need [Git](https://git-scm.com/downloads) installed on your computer. If you would rather not use Git, you can just download the code from GitHub above. From your command line:

```bash
# Clone this repository
$ git clone https://github.com/willtheorangeguy/Chrome-File-Directory.git

# Go into the repository
$ cd Chrome-File-Directory

# Run the webpage
$ index.html
```

However, **to make this your own directory**, either use the `index_chromium.html` file to create a self generating directory - or use the `index.html` file to create a custom directory listing with custom links.

### Basics

1. If you would rather have the styling for the page in its own separate location, copy the `style.css` file to that location and link it in the top of the `index.html` file. More instructions can be found in the [CUSTOMIZATION](https://github.com/willtheorangeguy/Chrome-File-Directory/tree/main/docs/CUSTOMIZATION.md) documentation page.

2. _Line 69_: Update the `example` placeholder text between the `<title>` tags with the actual directory name. This will be the title of the webpage.

```html
<title id="title">Index of example</title>
```

3. _Line 73_: Update the `:\directory` placeholder text between the `<h1>` tags with the actual directory path. This will be the title displayed on the page.

```html
<h1 id="header">Index of :\directory</h1>
```

4. _Line 74_: If this is a directory inside of another directory, remove the `style="display:none"` placeholder in the `div` tag.

```html
<div id="parentDirLinkBox" style="display:none">
```

5. _Line 75_: If this is a directory inside of another directory, change the `up/level` placeholder in the `href="..."` tag with the actual link to the folder above.
6. When you have customized the title, and added folder and file listings following the tutorials below, save the files and upload them to your web server.
7. You're all set!

## For a Folder

```html
<tr>
    <td data-value="Folder"><a class="icon dir" href="link/to/folder">Folder</a></td>
    <td class="detailsColumn" data-value="0"></td><td class="detailsColumn">MM/DD/YY, HH:MM:SS PM</td>
  </tr>
```

* Replace the `"Folder"` placeholder value (between the `data-value="..."` tag) with the real name of the folder.
* Replace the `"link/to/folder"` link (between the `href="..."` tag) with the actual link to the folder.
* Replace the `Folder` placeholder name (between the `<a>...</a>` tag) with the real name of the folder.
* Replace the `MM/DD/YY, HH:MM:SS PM` placeholder date with the date the folder was uploaded.
* Add more of these rows as necessary.

## For a File

```html
<tr>
    <td data-value="File"><a class="icon file" draggable="true" href="link/to/file">File.txt</a></td>
    <td class="detailsColumn">File</td><td class="detailsColumn">0.00 MB</td><td class="detailsColumn">MM/DD/YY, HH:MM:SS PM</td>
  </tr>
```

* Replace the `"File"` placeholder value (between the `data-value="..."` tag) with the real name of the file.
* Replace the `"link/to/file"` link (between the `href="..."` tag) with the actual link to the file.
* Replace the `File.txt` placeholder name (between the `<a>...</a>` tag) with the real name and extension of the file.
* Replace the `File` placeholder text with the actual file type.
* Replace the `0.00 MB` placeholder size with the real size of the file.
* Replace the `MM/DD/YY, HH:MM:SS PM` placeholder date with the date and time the file was uploaded.
* Add more of these rows as necessary.

## Support

Further customization options for different types of files and folder structures can be found in [`CUSTOMIZATION.md`](https://github.com/willtheorangeguy/Chrome-File-Directory/tree/main/docs). More documentation is available in the **[Documentation](https://github.com/willtheorangeguy/Chrome-File-Directory/tree/main/docs)** and on the **[Wiki](https://github.com/willtheorangeguy/Chrome-File-Directory/wiki)**. If more support is required, please open a **[GitHub Discussion](https://github.com/willtheorangeguy/Chrome-File-Directory/discussions/new)** or join our **[Discord](https://discord.gg/b7XPBfzZPC)**.

## Contributing

Please contribute using [GitHub Flow](https://guides.github.com/introduction/flow). Create a branch, add commits, and [open a pull request](https://github.com/willtheorangeguy/Chrome-File-Directory/compare).

Please read [`CONTRIBUTING`](CONTRIBUTING.md) for details on our [`CODE OF CONDUCT`](CODE_OF_CONDUCT.md), and the process for submitting pull requests to us.

## Changelog

See the [`CHANGELOG`](CHANGELOG.md) file for details.

## Credits

This software uses the following open source packages, projects, services or websites:

<!-- Credits Table -->
<table>
  <tr>
    <th align="center"><img src="https://github.githubassets.com/images/modules/logos_page/GitHub-Mark.png" width="200" height="200" alt="GitHub"/></th>
    <th align="center"><img src="https://pbs.twimg.com/profile_images/1069553420854591489/stZUQMcC_400x400.jpg" width="200" height="200" alt="W3C"/></th>
    <th align="center"><img src="https://videos.w3schools.com/files/images/w3schools_logo_500_04AA6D.png" width="250" height="150" alt="W3Schools"/></th>
    <th align="center"><img src="https://upload.wikimedia.org/wikipedia/commons/thumb/2/28/Chromium_Logo.svg/800px-Chromium_Logo.svg.png" width="250" height="200" alt="Chrome"/></th>
  </tr>
  <tr>
    <td align="center">GitHub</td>
    <td align="center">W3C</td>
    <td align="center">W3Schools</td>
    <td align="center">Chromium</td>
  </tr>
  <tr>
    <td align="center"><a href="https://github.com/">Web</a> - <a href="https://github.com/pricing">Plans</a></td>
    <td align="center"><a href="https://www.w3.org">Web</a> - <a href="https://www.w3.org/support/">Donate</a></td>
    <td align="center"><a href="https://www.w3schools.com">Web</a> - <a href="https://www.w3schools.com/pro/index.php">Pro</a></td>
    <td align="center"><a href="https://www.chromium.org/chromium-projects/">Web</a></td>
  </tr>
</table>

## Contributors

* [@willtheorangeguy](https://github.com/willtheorangeguy) - Sponsor on [PayPal](https://paypal.me/wvdg44?country.x=CA&locale.x=en_US)

## You may also like...

* [Running Calculator](https://github.com/willtheorangeguy/Running-Calculator) - A running speed calculator for any unit of distance.
* [PyWorkout](https://github.com/willtheorangeguy/PyWorkout) - A minimal CLI to keep you inspired during your workout! Easily used and customized, with support for multiple workout plans, different muscle groups and video workouts.
* [PyAvatar](https://github.com/willtheorangeguy/PyAvatar) - Easily display all of your creative avatars to keep them consistent across websites.

## License

**The website code in this repository is created by the [Chromium Development Team](https://www.chromium.org/Home/) and maintained by Google. The browser is released under the BSD 2-Clause “Simplified” License, and this project follows those licensing guidelines.**

This project is licensed under the [BSD 2-Clause “Simplified” License](https://choosealicense.com/licenses/bsd-2-clause/) - see the [`LICENSE`](LICENSE.md) file for details. See the [Privacy Policy](https://github.com/willtheorangeguy/Chrome-File-Directory/blob/main/docs/legal/PRIVACY.md) and [Terms and Conditions](https://github.com/willtheorangeguy/Chrome-File-Directory/blob/main/docs/legal/TERMS.md) for legal information.
