# Chrome File Directory Customization

The Chrome File Directory has been designed to be heavily customizable. More file and folder listings can be added, and directory paths can be changed, and the icons for each type of file can be changed. **Just search for and change the placeholder values in each code section.** Additionally, ensure that you have deleted all the extra file and folder rows that are unnecessary for your file listing, so not to confuse users.

All of these instructions require [a text editor](https://code.visualstudio.com/) to be installed.

## Basics

1. If you would rather have the styling for the page in its own separate location, copy the `style.css` file to that location and link it in the top of the `index.html` file. To do so, follow the steps below:
    1. Delete lines 9 through 68.
    2. Find the link to the `style.css` file.
    3. Add `<link rel="stylesheet" href="style.css">` to line 9.
    4. Update the link between the `href="..."` to the exact link to the `style.css` file.
    5. You're all set to have an external style sheet!

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

```html
    <a id="parentDirLink" href="up/level" class="icon up">
```

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

## Change Icons

The icons that are used to represent the different file types can also be changed. To add your own icons, follow these steps:

1. Find icons and save them as a `.ping` file. Ensure the icons are `16`x`16` pixels in size.
2. Move the icons to the `icons` folder.
3. Rename the icons to match the current icons.
4. You're all set!
