# Appcelerator Titanium Package for Visual Studio Code

Appcelerator Titanium build tools for [Visual Studio Code](https://code.visualstudio.com).

## Installation

### Development

* ``cd /path/to/extension`` and run ``npm install``
* Open project in VS Code
* Debug > Run. This will open a VS Code window with extension loaded

### Testing

* Create symlink to ``~/.vscode/extensions/``
* ``cd /path/to/extension`` and run ``npm inatall``
* Restart VS Code

## Status

Feature                             | Status    | Notes
---                                 | ---      	| ---
**Project support**                 | 🔜        |
App                                 | ✅        |
Native module                       | ⛔️        |
**Build**                           | 🔜        | VS Code does not allow a custom toolbar, interaction through command palette
Keymap                              | ✅        |
Command palette                     | ✅        |
Console output                      | ✅        | Using built-in console
Local development (iOS)             | ✅        |
Local development (Android)         | ✅        |
Distribution (iOS)                  | ✅        |
Distribution (Android)              | ⛔️        | Need to look at entering keystore credentials
**Project creation**                | ⛔️        |
**Alloy component generation**      | ⛔️        |
**Editor tools**					| ✅		   |
Code highlighting					| ✅		   | Built-in support for JS and XML, added launguage support for TSS
Code completion	                    | ✅        | Functionally complete but needs some refactoring
Generate code completions list      | ✅️		|
Jump to definition  	            | ✅		   | Path values are not highlighted correctly; images are previewed on hover
Open related files                  | ✅		   |
Snippets							| ✅		   |

## Open a Titanium project

File > Open Workspace... > Browse to Titanium project

From the CLI:

```
code /path/to/titanium/project
```

## Features

### Commands

Command                           | Keymap                | Description
---                               | ---                   | ---
Run                               | `cmd/ctrl-alt-enter`  | Build and run on simulator or device
Distribute                        | -                     | Build project for Ad-Hoc or App Store distribution
Stop                              | `cmd/ctrl-alt-.`      | Stop the current build
Set log level                     | -                     | Set the output log level
Init                              | -                     | Reload Appcelerator environment information
Generate autocomplete suggestions | -                     | Build autocomplete database for current default SDK version
Open related view                 | `cmd/ctrl-alt-v`      | Open the related Alloy XML file
Open related style                | `cmd/ctrl-alt-s`      | Open the related Alloy TSS file
Open related controller           | `cmd/ctrl-alt-x`      | Open the related JavaScript file
Toggle related files              | `cmd/ctrl-alt-a`      | Toggle the related Alloy XML, TSS and Javascript files

### Build tools

Use the command palette and commands listed above to build and run your Appcelerator project. Follow instructions to select platform, target and (if appropriate) code signing. The last build destination is saved for quick recall.

By default the integrated terminal is used to execute the build command.

### Autocompletion

Autocompletion support is provided to help speed up development by providing quick references to Titanium APIs and Alloy markup as well as references to modules, widgets and assets within your project.

#### Generation

On initial launch, autocomplete suggestions are generated for the current selected Titanium SDK. You can check and set this using the CLI:

```
$ appc ti sdk

...

Installed SDKs:
   7.0.0.GA [selected]  7.0.0.GA
```

```
$ appc ti sdk select
```

Autocomplete suggestions can be regenerated by running the `Generate autocomplete suggestions` command from the command palette.

#### Titanium and Alloy

Titanium APIs and Alloy markup suggestions are provided in Titanium JavaScript and Alloy XML and TSS files. This includes classes, properties, methods and events.

#### Project references

Suggestions for other controllers, modules and widgets are presented when referencing through a Titanium function or Alloy markup.

#### Class and ID references

Suggestions for classes and IDs declared or defined in related Alloy XML and TSS files are presented.

#### Images

Image suggestions are presented where appropriate.

### Open related files

Opening related Alloy files is supported (see above commands list).

* From View, open related Style and/or Controller
* From Style, open related View and/or Controller
* From Controller, open related View and/or Style

### Jump-to-definition

Jump-to-definition support is provided for quickly accessing the definiion or usage of Alloy markup and to easily generate new definitions. Images can be previewed inline.

#### Alloy

From Views, click through to style definitions for tags, classes and IDs, in related or global TSS. Click through to event definitions in the related controller.

A prompt is displayed to generate undefined styles or functions.

#### Strings

Click on localised string references to jump to their definition. The option to generate undefined strings is provided.

#### Images

Click on an image path to open a preview. For iOS, where multiple scaled images exist with the same name the first is opened (e.g. @2x).

### Snippets

Code snippets for common Alloy and Titanium APIs are provided for use in Alloy controllers and modules. A description of the snippet and link to documentation are provided where appropriate. Type the prefix and the autocomplete overlay will be displayed with matching snippets.

Prefix          | Description
---             | ---
`tidebug`       | Debug log message
`tierror`       | Error log message
`tiinfo`        | Info log message
`tiwarn`        | Warn log message
`titrace`       | Trace log message
`tiaddevent`    | Add event listener
`tiremevent`    | Remove event listener
`tifireevent`   | Fire event
`tialert`       | Show alert dialog
`tiopt`         | Show option dialog
`tianim`        | View animation
`tifile`        | Open file
`tisound`       | Play sound
`tiaudio`       | Play local or remote audio
`tivideo`       | Play local or remove video
`ticamera`      | Open camera
`alglo`         | Alloy Globals object
`alcfg`         | Alloy CFG object
`alcon`         | Alloy create controller function
`alcol`         | Alloy create collection function
`almod`         | Alloy create model function
`alwid`         | Alloy create widget function
`ifios`         | iOS conditional statement
`ifand`         | Android conditional statement
`ifwin`         | Windows conditional statement