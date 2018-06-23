# [VS Code](https://code.visualstudio.com) 小贴士

# 内容目录

1. <a href="#basics">基本</a>
2. <a href="#customization">个性化</a>
3. <a href="#extensions">插件扩展</a>
4. <a href="#file-and-folder-management">文件及文件夹管理</a>
5. <a href="#editing-hacks">高级编辑操作</a>
6. <a href="#intellisense">智能提示</a>
7. <a href="#snippets">代码片段生成</a>
8. <a href="#git-integration">Git集成</a>
9. <a href="#debugging">调试</a>
10. <a href="#task-runner">Task runner</a>
11. <a href="#other-resources">其他资源</a>

> 文中提到的快捷键操作可能会和最新版本的软体有所不同。请查看默认的快捷键配置文件。

# 基本

## 打开命令面板

通过命令面板可以很方便的访问到VS Code所有的可用命令

> Mac: <kbd>cmd+shift+p</kbd> or <kbd>f1</kbd>



> Windows / Linux: <kbd>ctrl+shift+p</kbd> 或 <kbd>f1</kbd>

![command palette](/media/command_p.png)

## Reference keybindings

在命令面板中的所有命令都有与之对应的快捷键。如果你忘记快捷键是什么，可以打开命令面板来查看。

## 快捷开启

快速的打开文件和运行相关命令(操作如下)

> Mac: <kbd>cmd+p</kbd>



> Windows / Linux: <kbd>ctrl+p</kbd>

在快捷开启输入框中键入“?”来浏览相关帮助信息。

## 将命令复制并粘贴在快速打开输入框中

先按<kbd>cmd+p</kbd>唤出快速打开输入框然后将命令粘贴进去。这一技巧在使用插件商城时尤为有用 。

![marketplace copy and paste](/media/mp_copy_paste.png)

## 命令行操作

打开命令面板 (<kbd>F1</kbd>) 然后键入"shell command"。运行"Shell Command: Install 'code' command in PATH"这一命令。 

![shell command](/media/setup_shell-command.png)


```bash
# 创建新窗口
code -n

# 改变语言
code --locale=es

# 创建一个比对编辑器
code --diff <file1> <file2>

# 浏览帮助选项
code --help
```

## .vscode 文件夹

工作空间的文件都在 `.vscode`文件夹中。比如 `tasks.json` 是关于task runner的配置文件， `launch.json` 是关于debugger的配置文件。

## 状态条Status bar decorations

**错误和警告**

> Mac: <kbd>shift+cmd+m</kbd>



> Windows / Linux: <kbd>ctrl+shift+m</kbd>

快速跳转到项目中的报错位置。

按 <kbd>f8</kbd> 或 <kbd>shift+f8</kbd>跳转到下一个报错位置

![status errors and warnings](/media/status_errors_warnings.png)

**更新扩展插件**

相关标识会出现在状态条的左下位置。

![extension actions](/media/extension_actions.png)

**改变语言模式**

> Mac: <kbd>cmd+k m</kbd>



> Windows / Linux: <kbd>ctrl+k m</kbd>

![change syntax](/media/change_syntax.gif)

# 个性化

关于个性化有非常多的内容，如果想了解更多请查阅[文档](http://code.visualstudio.com/docs/customization/overview)。

## 定制编辑器

打开 `settings.json` 

> Mac: <kbd>cmd+,</kbd>



> Windows / Linxu: File -> Preferences -> User Settings

*改变字体大小*

```json
"editor.fontSize": 18
```

*改变缩进的字符长度*

```json
"editor.tabSize": 4
```

*Spaces or tabs*

```json
"editor.insertSpaces": true
```

*文件或者文件夹忽略*

把这些文件或者文件夹从你的编辑器窗口移除。 

```json
"files.exclude": {
		"somefolder/": true, 
		"somefile": true
}
```

把这些文件或者文件夹从搜索结果中移除。

```json
"search.exclude": {
    "someFolder/": true,
    "somefile": true
}
```

以及许多其他功能，[详情点击此处](http://code.visualstudio.com/docs/customization/userandworkspace)。

## 预览主题

![Preview themes](/media/preview_themes.gif)

## json 合法性校验

更多类型的json配置文件的合法性检验默认开启,你也可以在`settings.json`里指定你自己的规则(JSON Schema)，如果想进一步了解这种检验规则的规则，[请点击此处](https://spacetelescope.github.io/understanding-json-schema/)。

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

这个规则也可以引用你的工作空间

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

或者一个自定义的规则

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

在[文档](http://code.visualstudio.com/docs/languages/json)中了解更多.

# 插件扩展

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
