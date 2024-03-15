<p align="center">
	<!--
  <a href="https://example.com/">
    <img src="https://via.placeholder.com/72" alt="JSON Menu" width=72 height=72>
  </a>
	-->

  <h3 align="center">JSON Menu</h3>

  <p align="center">
    The easiest way to create interactive console menus in Python
    <br>
    <a href="https://github.com/xavi-burgos99/jsonmenu/issues/new?template=bug.md">Report bug</a>
    ·
    <a href="https://github.com/xavi-burgos99/jsonmenu/issues/new?template=feature.md&labels=feature">Request feature</a>
  </p>
</p>


## Table of contents

- [Table of contents](#table-of-contents)
- [Introduction](#introduction)
- [Installation](#installation)
- [How to use](#how-to-use)
- [Options](#options)
	- [Custom language](#custom-language)
	- [Custom theme](#custom-theme)
- [What's included](#whats-included)
- [Bugs and feature requests](#bugs-and-feature-requests)
- [Contributing](#contributing)
- [Creator](#creator)


## Introduction

JSON Menu is a Python library created by [Xavi Burgos](https://xburgos.es/) that lets you create interactive console menus from basic JSON structures. With just a few lines of code, you can build user-friendly interfaces for your Python scripts.

The menu generated by JSON Menu will be displayed as the following example:

```text
┌─────────────────────────────┐
│        My first menu        │
├─────────────────────────────┤
│ 1. My first action          │
│ 2. Submenu                  │
│ 0. Exit                     │
└─────────────────────────────┘

Select an option: 
```


## Installation

To install JSON Menu, you can use the following [pip](https://pip.pypa.io/en/stable/) command:

```bash
pip install jsonmenu
```

Alternatively, you can clone the repository and run the following command:

```bash
python setup.py install
```

or include the 'jsonmenu.py' file in your project and import it as a module in your Python scripts.

```python
from jsonmenu import JsonMenu
```


## How to use

To create a menu, you need to define a JSON structure with the following format:

```python
menu_data = [
	{
		"label": "My first action",
		"action": my_function
	},
	{
		"label": "Submenu",
		"submenu": [
			{
				"label": "Option 1",
				"action": custom_function_1
			},
			{
				"label": "Option 2",
				"action": custom_function_2
			}
		]
	}
]
```

Also, you can add an options dictionary to customize the menu, explained at [options](#options) section.

```python
custom_options = {
	"language": "es",
	"theme": "rounded"
}
```

Then, you can create the menu with the following code:

```python
jm = JsonMenu("My first menu", menu_data, custom_options)
jm.show()
```


## Options

The options dictionary allows you to customize the appearance and behavior of the menu. The following options are available:

| Option | Description | Default value | Possible values |
| --- | --- | --- | --- |
| `back_menu` | Previous menu to return when the user selects the `0` option. If not defined, the menu will close. | `None` | `JsonMenu` object |
| `clear` | Clear the console before showing the menu. This option is useful to avoid cluttering the console with previous outputs. | `False` | `True`, `False` |
| `debug` | Show debug information in the console. This option is useful for development and testing. Warnings will not be displayed if `clear` option is enabled (console is cleared before showing the menu). | `False` | `True`, `False` |
| `width` | Width of the menu in characters. | `31` | `int` |
| `language` | Language of the menu. Also a dictionary could be passed, and the menu will be use the provided custom translations. | `en` | `ar`, `ca`, `de`, `en`, `es`, `fr`, `hi`, `it`, `ja`, `ko`, `nl`, `pt`, `ru`, `sv`, `tr`, `zh`, [\<custom dictionary\>](#custom-language) |
| `theme` | Theme of the menu. Also a dictionary could be passed, and the menu will be use the provided custom theme. | `unicode` | `ascii`, `unicode`, `bold`, `double`, `rounded`, `dotted`, `striped`, [\<custom dictionary\>](#custom-theme) |


### Custom language

A custom language dictionary can be passed to the `language` option. The dictionary must contain the following keys:

| Key | Description | English value |
| --- | --- | --- |
| `back` | Text for the back option. | Back |
| `exit` | Text for the exit option. | Exit |
| `invalid_option` | Text for the invalid option message. | Invalid option |
| `select_option` | Text for the select option message. | Select an option |
| `press_enter` | Text for the press enter to continue message. | Press "Enter" to continue |


### Custom theme

A custom theme dictionary can be passed to the `theme` option. The dictionary must contain the following keys:

| Key | Description | Unicode value |
| --- | --- | --- |
| `tl` | Top left corner of the menu. | `┌` |
| `tr` | Top right corner of the menu. | `┐` |
| `cl` | Center left corner of the menu. | `├` |
| `cr` | Center right corner of the menu. | `┤` |
| `bl` | Bottom left corner of the menu. | `└` |
| `br` | Bottom right corner of the menu. | `┘` |
| `h` | Horizontal line of the menu. | `─` |
| `v` | Vertical line of the menu. | `│` |


## What's included

Within the download you'll find the following directories and files, logically grouping common assets. You'll see something like this:

```text
jsonmenu/
├── jsonmenu
│   ├── __init__.py
│   └── jsonmenu.py
├── setup.py
├── CONTRIBUTING.md
├── LICENSE
└── README.md
```


## Bugs and feature requests

Have a bug or a feature request? Please first read the [issue guidelines](https://github.com/xavi-burgos99/jsonmenu/blob/main/CONTRIBUTING.md) and search for existing and closed issues. If your problem or idea is not addressed yet, [please open a new issue](https://github.com/xavi-burgos99/jsonmenu/issues/new).


## Contributing

Please read through our [contributing guidelines](https://github.com/xavi-burgos99/jsonmenu/blob/main/CONTRIBUTING.md). Included are directions for opening issues, coding standards, and notes on development.


## Creator

**Xavier Burgos**
 - Website: <https://xburgos.es/>
 - GitHub: <https://github.com/xavi-burgos99/>
 - LinkedIn: <https://linkedin.com/in/xavi-burgos/>

