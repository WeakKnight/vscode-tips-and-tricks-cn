# [VS Code](https://code.visualstudio.com) Tips and Tricks

# Table of Contents

1. <a href="#basics">Basics</a>
2. <a href="#customization">Customization</a>
3. <a href="#extensions">Extensions</a>
4. <a href="#file-and-folder-management">File and folder management</a>
5. <a href="#editing-hacks">Editing hacks</a>
6. <a href="#intellisense">Intellisense</a>
7. <a href="#snippets">Snippets</a>
8. <a href="#git-integration">Git integration</a>
9. <a href="#debugging">Debugging</a>
10. <a href="#task-runner">Task runner</a>
11. <a href="#other-resources">Other Resources</a>

> The key bindings below may or may not be accurate with the latest build. Check on the Default Keyboard shortcuts file. 

# Basics

## Open command palette

Easy access to all commands available in VS Code. 

> Mac: <kbd>cmd+shift+p</kbd> or <kbd>f1</kbd>

> Windows / Linux: <kbd>ctrl+shift+p</kbd> or <kbd>f1</kbd>

![command palette](/media/command_p.png)

## Reference keybindings

All of the commands are in the command palette with the associated key binding (if it exists). If you forget what the key binding is use the command palette to help you out. 

## Quick open

Quickly open files and run commands (see below). 

> Mac: <kbd>cmd+p</kbd>

> Windows / Linux: <kbd>ctrl+p</kbd>

Type "?" to view help suggestions. 

## Copy and paste commands into quick open

<kbd>cmd+p</kbd> then paste the command you want to run. This is especially
useful with the extension marketplace. 

![marketplace copy and paste](/media/mp_copy_paste.png)

## Command line arguments

Open the command palette (<kbd>F1</kbd>) and type "shell command". Hit enter
to execute "Shell Command: Install 'code' command in PATH". 

![shell command](/media/setup_shell-command.png)


```bash
# create a new window
code -n

# change the language
code --locale=es

# open diff editor
code --diff <file1> <file2>

# see help options
code --help
```

## .vscode folder

Workspace specific files are in `.vscode`. For example, `tasks.json` for the Task Runner and `launch.json` for the debugger.

## Status bar decorations

**Errors and Warnings**

> Mac: <kbd>shift+cmd+m</kbd>

> Windows / Linux: <kbd>ctrl+shift+m</kbd>

Quickly jump to errors and warnings in the project. 

Cycle through errors with <kbd>f8</kbd> or <kbd>shift+f8</kbd>

![status errors and warnings](/media/status_errors_warnings.png)

**Update extensions**

Badges will appear in the bottom left of the status bar. 

![extension actions](/media/extension_actions.png)

**Change language mode**

> Mac: <kbd>cmd+k m</kbd>

> Windows / Linux: <kbd>ctrl+k m</kbd>

![change syntax](/media/change_syntax.gif)

# Customization

Lots of things you can do here. Check out the full [documentation](http://code.visualstudio.com/docs/customization/overview). 

## Customize editor

Open `settings.json` 

> Mac: <kbd>cmd+,</kbd>

> Windows / Linxu: File -> Preferences -> User Settings

*Change the font size*

```json
"editor.fontSize": 18
```

*Change the size of tab characters*

```json
"editor.tabSize": 4
```

*Spaces or tabs*

```json
"editor.insertSpaces": true
```

*Ignore files / folders*

Removes these files / folders from your editor window. 

```json
"files.exclude": {
		"somefolder/": true, 
		"somefile": true
}
```

Remove these files / folders from search results. 

```json
"search.exclude": {
    "someFolder/": true,
    "somefile": true
}
```

And many, many [others](http://code.visualstudio.com/docs/customization/userandworkspace).

## Preview themes

![Preview themes](/media/preview_themes.gif)

## json validation

Enabled by default for many files. Create your own schema and validation in `settings.json`

```json
"json.schemas": [
    {
        "fileMatch": [
            "/bower.json"
        ],
        "url": "http://json.schemastore.org/bower"
    }
]
``` 

or for a schema defined in your workspace

```json
"json.schemas": [
    {
        "fileMatch": [
            "/foo.json"
        ],
        "url": "./myschema.json"
    }
]
``` 

or a custom schema

```json
"json.schemas": [
    {
        "fileMatch": [
            "/.myconfig"
        ],
        "schema": {
            "type": "object",
            "properties": {
                "name" : {
                    "type": "string",
                    "description": "The name of the entry"
                }
            }
        }
    },
```

See more in the [documentation](http://code.visualstudio.com/docs/languages/json).

# Extensions

## Contribution points

[Documentation on contribution points](http://code.visualstudio.com/docs/extensionAPI/extension-points).

* configuration
* commands
* keybindings
* languages
* debuggers
* grammars
* themes
* snippets
* jsonValidation

## Find extensions

1. The official VS Code [marketplace](https://marketplace.visualstudio.com/vscode).
2. Search in product (see below)
3. View extension recommendations (see below)
4. Community curated extensions like [awesome-vscode](https://github.com/viatsko/awesome-vscode).

## Install extensions

> Mac: <kbd>cmd+shift+p</kbd> 

> Windows / Linux: <kbd>ctrl+shift+p</kbd>

then type "ext install". Select the extension you want and hit <kbd>enter</kbd>

![install extension](/media/install_extension.gif)

## Extension recommendations

> Mac: <kbd>cmd+shift+p</kbd>

> Windows / Linux: <kbd>ctrl+shift+p</kbd>

then type "ext", then select "Show Extension Recommendations"

![extension recommendations](/media/extension_recommendations.gif)

## Uninstall an extension

> Mac: <kbd>cmd+shift+p</kbd>

> Windows / Linux: <kbd>ctrl+shift+p</kbd>

then type "ext", then select "Show Installed Extensions". 
Click the "x" on the bottom right of the extension card. 

![uninstall extension](/media/uninstall_extension.gif)

# File and folder management

## OS X layout

Using mission control, put a terminal window on the same screen as VS Code. Wala! You know have an integrated terminal. 

![OS X layout](/media/osx_layout.png)

## Autosave

Open `settings.json` with <kbd>cmd+,</kbd>

```json
"files.autoSave": "afterDelay"
```

## Toggle sidebar

> Mac: <kbd>cmd+b</kbd>

> Windows / Linux: <kbd>ctrl+b</kbd>

![toggle side bar](/media/toggle_side_bar.gif)

## Side by side editing

> Mac: <kbd>cmd+\\</kbd> or <kbd>cmd</kbd> then click a file from the file browser. 

> Windows / Linux: <kbd>ctrl+\\</kbd>

![split editors](/media/split_editor.gif)

## Switch between editors

> Mac: <kbd>cmd+1</kbd>, <kbd>cmd+2</kbd>, <kbd>cmd+3</kbd>

> Windows / Linux: <kbd>ctrl+1</kbd>, <kbd>ctrl+2</kbd>, <kbd>ctrl+3</kbd>

![navigate editors](/media/navigate_editors.gif)

## History

Navigate entire history with <kbd>ctrl+tab</kbd>

Navigate back.

> Mac: <kbd>ctrl+-</kdbd>

> Windows / Linux: <kbd>alt+left</kbd>

Navigate Forward.

> Mac: <kbd>ctrl+shift+up</kbd>

> Windows / Linux: <kbd>alt+right</kbd>

![navigate history](/media/navigate_history.gif)

## Navigate to a file

> Mac: <kbd>cmd+e</kbd> or <kbd>cmd+p</kbd>

> Windows / Linux: <kbd>ctrl+e</kbd> or <kbd>ctrl+p</kbd>

![navigate to file](/media/navigate_to_file.gif)

## File associations

Setup language associations for files that aren't detected accurately (i.e. many config files). 

```json
"file.associations": {
    ".eslintrc": "json"
}
```

# Editing hacks

## Bracket matching

More in [documentation](http://code.visualstudio.com/docs/editor/editingevolved#_bracket-matching).

> Mac: <kbd>up+cmd+\\<kbd>

> Windows / Linux: <kbd>ctrl+shift+\\</kbd>

![bracket matching](/media/bracket_matching.gif)

## Multi cursor selection

More in [documentation](http://code.visualstudio.com/docs/editor/editingevolved#_selection-multicursor).

> Mac: <kbd>opt+cmd+up</kbd> or <kbd>opt+cmd+down</kbd>

> Windows / Linux: <kbd></kbd>

![multi cursor](/media/multi_cursor.gif)

![multi cursor second example](/media/editingevolved_multicursor.gif)

Add more cursors to current selection.

![add cursor to all occurrences of current selection](/media/add_cursor_current_selection.gif)

## Copy line

> Mac: <kbd>opt+shift+up</kbd> or <kbd>opt+shift+down</kbd>

> Windows / Linux: <kbd>shift+alt+down</kbd> or <kbd>shift+alt+up</kbd>

![copy line down](/media/copy_line_down.gif)

## Shrink / expand selection

More in [documentation](http://code.visualstudio.com/docs/editor/editingevolved#_selection-multicursor)

> Mac: <kbd>ctrl+shift+cmd+left</kbd> or <kbd>ctrl+shift+cmd+right</kbd>

> Windows / Linux: <kbd>shift+alt+left</kbd> or <kbd>shift+alt+right</kbd>

![shrink expand selection](/media/shrink_expand_selection.gif)

## Find by symbol

> Mac: <kbd>cmd+shift+o</kbd>

> Windows: <kbd>ctrl+shift+o</kbd>

![Find by symbol](/media/find_by_symbol.gif)

## Navigate to a specific line

> Mac: <kbd>ctrl+g</kbd> or <kbd>cmd+p, :</kbd>

> Windows / Linux: <kbd>ctrl+g</kbd>

![navigate to line](/media/navigate_to_line.gif)

## Undo cursor position

> Mac: <kbd>cmd+u</kbd>

> Windows / Linux: <kbd>ctrl+u</kbd>

![undo cursor position](/media/undo_cursor_position.gif)

## Move line up and down

> Mac: <kbd>opt+up</kbd> or <kbd>opt+down</kbd>

> Windows / Linux: <kbd>alt+up</kbd> or <kbd>alt+down</kbd>

![move line up and down](/media/move_line.gif)

## Trim trailing whitespace

> Mac: <kbd>shift+up+x</kbd>

> Windows / Linux: <kbd>ctrl+shift+x</kbd>

![trailing whitespace](/media/trim_whitespace.gif)

## Code formatting

> Mac / Windows / Linux: <kbd>shift+alt+f</kbd>

![code formatting](/media/code_formatting.gif)

## Code folding

> Mac: <kbd>shift+cmd+\[</kbd> and <kbd>shift+cmd+\]</kbd>

> Windows / Linux: <kbd>ctrl+shift+\[</kbd> and <kbd>ctrl+shift+\]</kbd>

![code folding](/media/code_folding.gif)

## Select current line

> Mac: <kbd>cmd+i</kbd>

> Windows / Linux: <kbd>ctrl+i</kbd>

![select current line](/media/select_current_line.gif)

## Navigate to beginning and end of file

> Mac: <kbd>cmd+up</kbd> and <kbd>cmd+down</kbd>

> Windows / Linux: <kbd>ctrl+up</kbd> and <kbd>ctrl+down</kbd>

![navigate to beginning and end of file](/media/beginning_end_file.gif)

## Toggle README preview

In a markdown file use 

> Mac: <kbd>shift+cmd+v</kbd>

> Windows / Linux: <kbd>ctrl+shift+v</kbd>

![toggle readme preview](/media/toggle_preview.gif)

# Intellisense

Anytime, try <kbd>ctrl+space</kbd> to trigger the suggest widget. This might be the most important tip of them all. 

![intellisense](/media/intellisense.gif)

You can view available methods, parameter hints, short documentation, etc. 

## Peek

Select a symbol then type <kbd>alt+f12</kbd>. Alternatively, you can use the context menu. 

![peek](/media/peek.gif)

## Go to definition

Select a symbol then type <kbd>f12</kbd>. Alternatively, you can use the context menu. 

![go to definition](/media/goto_definition.gif)

## Find all references

Select a symbol then type <kbd>shift+f12</kbd>. Alternatively, you can use the context menu. 

![find all references](/media/find_all_references.gif)

## Rename symbol

Select a symbol then type <kbd>f2</kbd>. Alternatively, you can use the context menu. 

![rename symbol](/media/rename_symbol.gif)


## jsconfig.json

Use ES6 by configuring jsconfig.json in the root of your javascript source files. 

```json
{
    "compilerOptions": {
        "target": "ES6",
        "module": "commonjs"
    }, "exclude": [
        "npm_modules"
    ]
}
```

## .eslintrc.json

Install [eslint extension](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint). Configure 
your linter however you'd like. Specification is [here](http://eslint.org/docs/user-guide/configuring). 

Here is configuration to use es6. 

```json
{
    "env": {
        "browser": true,
        "commonjs": true,
        "es6": true,
        "node": true
    },
    "parserOptions": {
        "ecmaVersion": 6,
        "sourceType": "module",
        "ecmaFeatures": {
            "jsx": true,
            "classes": true,
            "defaultParams": true
        }
    },
    "rules": {
        "no-const-assign": 1,
        "no-extra-semi": 0,
        "semi": 0,
        "no-fallthrough": 0,
        "no-empty": 0,
        "no-mixed-spaces-and-tabs": 0,
        "no-redeclare": 0,
        "no-this-before-super": 1,
        "no-undef": 1,
        "no-unreachable": 1,
        "no-use-before-define": 0,
        "constructor-super": 1,
        "curly": 0,
        "eqeqeq": 0,
        "func-names": 0,
        "valid-typeof": 1
    }
}
```

## package.json

See intellisense for your package.json file. 

![package json intellisense](/media/package_json_intellisense.gif)

## Install typings

Install [typings](https://github.com/typings/typings) to bring in the `.d.ts` files which power javascript intellisense. 

```bash
npm install typings --global

# Search for definitions.
typings search tape

# Find an available definition (by name).
typings search --name react

# Install typings (DT is "ambient", make sure to enable the flag and persist the selection in `typings.json`).
typings install react --ambient --save
```

`install` will create a typings folder. VS Code will reference the `.d.ts` files for intellisense. 

## Emmet syntax

[Support for Emmet syntax](http://code.visualstudio.com/docs/languages/html#_emmet-snippets).  

![emmet syntax](/media/emmet_syntax.gif)

# Snippets

## Create custom snippets

`File -> Preferences -> User Snippets`, select the language, and create a shippet. 

```json
"create component": {
    "prefix": "component",
    "body": [
        "class $1 extends React.Component {",
        "",
        "	render() {",
        "		return ($2);",
        " 	}",
        "",
        "}"
    ]
},
```

See more details in [documentation](http://code.visualstudio.com/docs/customization/userdefinedsnippets#_creating-your-own-snippets). 

# Git Integration

Excellent integration for entire Git workflow. 

## Diffs

Click Git icon then select the file to diff. 

![git icon](/media/git_icon.png)

**Side by side**

Default is side by side diff. 

![git diff side by side](/media/git_side_by_side.png)

**Inline view**


Toggle inline view by clicking more button in the top right. 

![more git button](/media/more_button.png)

![git inline](/media/git_inline.png)

## Branches

Easily switch between branches via the status bar. 

![switch branches](/media/switch_branches.gif)

## Staging

**Stage all**

Hover over the number of files and click the plus button. 

![git stage all](/media/git_stage_all.gif)

**Stage selected**

Stage a portion of a file by selecting that file (using the arrows) and then staging 
"selected lines" via the more button. 

![git stage selected](/media/git_stage_selected.gif)

## Undo last commit

![undo last commit](/media/undo_last_commit.gif)

## See Git output

Sometimes I want to see what my tool is doing. Visual Studio Code makes it easy to see 
what git commands are running. This is helpful when learning git or debugging a difficult 
source control issue. 

> Mac: <kbd>shift+cmd+u</kbd> 

> Windows / Linux: <kbd>ctrl+shift+u</kbd>

to run `toggleOutput`. Select Git in the dropdown.

## Gutter indicators

View diff decorations in editor. See [documentation](http://code.visualstudio.com/docs/editor/editingevolved#_gutter-indicators) for more details. 

![git gutter indicators](/media/editingevolved_gutter.png)

## Resolve merge conflicts

During a merge click the git icon and make changes in the diff view. 

![git icon](/media/git_icon.png)

## Setup VS Code as default merge tool

```bash
git config --global merge.tool code
```

# Debugging

## Configure debugger

<kdb>f1</kdb> and select "Debug: Open Launch.json", select the environment. 
This will generate a `launch.json` file. Works out of the box as expected for
Node and other environments. May need some additional configuration for other languages.
See [documentation](http://code.visualstudio.com/docs/editor/debugging) for more details. 

![configure debugging](/media/configure_debug.gif)

## Breakpoints and stepping through

Place breakpoints next to the line number. Navigate forward with the debug widget. 

![debug](/media/node_debug.gif)

## Data inspection

Inspect variables in the debug panels and in the console. 

![data inspection](/media/debug_data_inspection.gif)

# Task Runner

## Auto detect tasks

<kbd>f1</kbd>, type "Configure Task", then select "Configure Task Runner". 
This will generate a task.json file with content like the following. See 
[documentation](http://go.microsoft.com/fwlink/?LinkId=733558) for more details.

```json
{
	// See http://go.microsoft.com/fwlink/?LinkId=733558
	// for the documentation about the tasks.json format
	"version": "0.1.0",
	"command": "npm",
	"isShellCommand": true,
	"showOutput": "always",
	"suppressTaskName": true,
	"tasks": [
		{
			"taskName": "install",
			"args": ["install"]
		},
		{
			"taskName": "build",
			"args": ["run", "build"]
		}
	]
}
```

There are occasionally issues with auto generation. Check out the documentation
for getting things to work properly. 

## Run tasks from command palette

<kbd>f1</kdb>, run the command "Run Task", and select the task you want to run. Terminate the running
task by running the command "Terminate Running Task"

![task runner](/media/task_runner.gif)


## Other Resources

* [vscode official docs](https://code.visualstudio.com/docs)
* [react sample app](https://github.com/Microsoft/vscode-react-sample)
* [vscode-tips](https://github.com/tstringer/vscode-tips)
