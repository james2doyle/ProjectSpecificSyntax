Project Specific Syntax Settings
================================

This package allows syntax settings to be specified per project.

In your `.sublime-project` file, you just need to add a `syntax_override` section, like so.

```javascript
{
    "folders":
    [
        // Your project folders
    ],

    "syntax_override": {
        "\\.html$": ["Handlebars", "grammars", "Handlebars"],
        "\\.js$": ["Babel", "JavaScript (Babel)"]
    }
}
```

The `syntax_override` section can contain as many key/value pairs as you like.

The easiest way to construct these key/value pairs is to follow these steps:

1. Open an existing file in your project.
2. Set the syntax you would like to use for that file with the `View > Syntax > ...` menus or the command palette.
3. Right click in the file editor area, and select the `Project Specific Syntax > Copy syntax setting to clipboard` menu item. This menu item is also available via the command palette.
4. Open your project file for editing via the `Project > Edit Project` menu or the command palette.
5. Paste the new key/value pair into the `syntax_override` section of your project file. Be sure to add any necessary commas to separate multiple key/value pairs so your project file is still valid JSON.

If you need more control, you can construct your own key/value pairs. The key should be a regular expression that will be matched against the name of the file. Note that the `.` in `.html` in the example above has to be escaped to `\.` since it will otherwise match any character. And since this is a JSON string, we need to escape the slash, so we end up with `\\.`.

The value in the key/value pair should be an array containing two or more strings. All but the last string in this array are the names of the package directories containing the syntax file and the last is the name of the syntax. Root around in Sublime Text's directory structure to find files that end with `.tmLanguage`. The names of these files (minus the `.tmLanguage` extension) are what you would use for the last string. Typically, you will only have two strings, a directory name and the syntax file name (minus `.tmLanguage` file extension), but this is dependent on the package's directory structure.

More info about projects and the project file format can be found at the [Sublime Text website](https://www.sublimetext.com/docs/3/projects.html) and at the [Sublime Text Unofficial Documentation website](http://docs.sublimetext.info/en/latest/file_management/projects.html).


## Installation

### By Package Control

1. Download & Install **`Sublime Text 3`** (https://www.sublimetext.com/3)
1. Go to the menu **`Tools -> Install Package Control`**, then,
    wait few seconds until the installation finishes up
1. Now,
    Go to the menu **`Preferences -> Package Control`**
1. Type **`Add Channel`** on the opened quick panel and press <kbd>Enter</kbd>
1. Then,
    input the following address and press <kbd>Enter</kbd>
    ```
    https://raw.githubusercontent.com/evandrocoan/StudioChannel/master/channel.json
    ```
1. Go to the menu **`Tools -> Command Palette...
    (Ctrl+Shift+P)`**
1. Type **`Preferences:
    Package Control Settings – User`** on the opened quick panel and press <kbd>Enter</kbd>
1. Then,
    find the following setting on your **`Package Control.sublime-settings`** file:
    ```js
    "channels":
    [
        "https://packagecontrol.io/channel_v3.json",
        "https://raw.githubusercontent.com/evandrocoan/StudioChannel/master/channel.json",
    ],
    ```
1. And,
    change it to the following, i.e.,
    put the **`https://raw.githubusercontent...`** line as first:
    ```js
    "channels":
    [
        "https://raw.githubusercontent.com/evandrocoan/StudioChannel/master/channel.json",
        "https://packagecontrol.io/channel_v3.json",
    ],
    ```
    * The **`https://raw.githubusercontent...`** line must to be added before the **`https://packagecontrol.io...`** one, otherwise,
      you will not install this forked version of the package,
      but the original available on the Package Control default channel **`https://packagecontrol.io...`**
1. Now,
    go to the menu **`Preferences -> Package Control`**
1. Type **`Install Package`** on the opened quick panel and press <kbd>Enter</kbd>
1. Then,
    search for **`ProjectSpecificSyntax`** and press <kbd>Enter</kbd>

See also:

1. [ITE - Integrated Toolset Environment](https://github.com/evandrocoan/ITE)
1. [Package control docs](https://packagecontrol.io/docs/usage) for details.

