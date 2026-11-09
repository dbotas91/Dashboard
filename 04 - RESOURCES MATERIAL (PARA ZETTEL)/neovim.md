# Knowledge Base
## Neovim + Java + TestNG + Selenide + Robot Framework + Security Testing

---

# Table of Contents

## Part I - Neovim & LazyVim

- #chapter-1---neovim-fundamentals
- #chapter-2---navigation-advanced
- #chapter-3---lazyvim
- #chapter-4---java-in-neovim

---

## Part II - Java Debugging

- #chapter-5---debugging-testng
- #chapter-6---dap
- #chapter-7---dap-ui
- #chapter-8---maven-debug
- #chapter-9---attach-dap

---

## Part III - Maven

- #chapter-10---common-commands
- #chapter-11---profiles

---

## Part IV - TestNG

- #chapter-12---suite-architecture
- #chapter-13---groups
- #chapter-14---parallel-execution

---

## Part V - Selenide

- #chapter-15---best-practices
- #chapter-16---page-objects

---

## Part VI - Java Patterns

- #chapter-17---fluent-apis
- #chapter-18---self-referencing-generics

---

## Part VII - Robot Framework

- #chapter-19---structure

---

## Part VIII - Performance Testing

- #chapter-20---locust

---

## Part IX - Security Testing

- #chapter-21---owasp-zap
- #chapter-22---burp-suite

---

## Part X - SAML Authentication

- #chapter-23---saml-flow

---

## Part XI - Troubleshooting

- #chapter-24---neovim
- #chapter-25---jdtls
- #chapter-26---debugging
- #chapter-27---selenide
- #chapter-28---generics

---

## Part XII - Cheatsheets

- #neovim-cheatsheet
- #maven-cheatsheet
- #dap-cheatsheet
- #testng-cheatsheet

---

## Part XIII - Lessons Learned

- #personal-notes

---

## Future Topics

- #future-sections

### Planned Additions

- Kubernetes
- Docker
- Azure DevOps
- CI/CD
- Playwright
- Pact
- Selenium Grid
- Grafana
- Prometheus
- Allure Reporting

---


# Chapter 1 - Neovim Fundamentals

#table-of-contents

---

# 1. Introduction

Neovim is a modern, extensible fork of Vim focused on performance, automation, scripting and integration with modern development tools.

For a Test Automation Engineer, Neovim provides:

- Fast keyboard-driven editing
- Integrated terminal
- Native LSP support
- Debugging via DAP
- Git integration
- Fuzzy finding
- Workspace navigation
- Java development support through JDTLS
- TestNG execution
- Maven execution
- Robot Framework integration

The objective of this chapter is to establish a strong foundation before moving to LazyVim, Java development, nvim-dap, and automation frameworks.

---

# 2. Neovim Modes

## 2.1 Normal Mode

Default mode.

Used for:

- Navigation
- Editing commands
- Copy/paste
- Search
- Window management

Example:

```vim
j
k
dd
yy
p
```

Return to Normal Mode:

```vim
Esc
```

---

## 2.2 Insert Mode

Used for writing text.

Enter:

```vim
i
```

Other useful variants:

```vim
i   Insert before cursor
a   Append after cursor
I   Start of line
A   End of line
o   New line below
O   New line above
```

Exit:

```vim
Esc
```

---

## 2.3 Visual Mode

Used for selecting text.

Character selection:

```vim
v
```

Line selection:

```vim
V
```

Block selection:

```vim
Ctrl-v
```

Examples:

```vim
vjjj
```

Select current line and next three lines.

---

## 2.4 Command Mode

Enter:

```vim
:
```

Examples:

```vim
:w
:q
:wq
:qa
```

---

# 3. Opening Files

## Open Current Directory

```bash
nvim .
```

---

## Open Specific File

```bash
nvim LoginPage.java
```

---

## Open Multiple Files

```bash
nvim file1.java file2.java
```

---

# 4. Saving And Quitting

## Save File

```vim
:w
```

---

## Save As

```vim
:w filename
```

---

## Quit

```vim
:q
```

---

## Save And Quit

```vim
:wq
```

or

```vim
ZZ
```

---

## Quit Without Saving

```vim
:q!
```

---

## Exit All

```vim
:qa
```

---

# 5. Navigation

## Move By Character

```vim
h
j
k
l
```

| Key | Action |
| --- | ------ |
| h   | Left   |
| j   | Down   |
| k   | Up     |
| l   | Right  |

---

## Move By Word

```vim
w
```

Next word.

```vim
b
```

Previous word.

```vim
e
```

End of word.

---

## Move Inside File

Beginning:

```vim
gg
```

End:

```vim
G
```

Specific line:

```vim
42G
```

Go to line 42.

---

## Move Within Line

Beginning:

```vim
0
```

First non-blank:

```vim
^
```

End:

```vim
$
```

---

# 6. Searching

## Search Forward

```vim
/login
```

---

## Search Backward

```vim
?login
```

---

## Next Match

```vim
n
```

---

## Previous Match

```vim
N
```

---

## Search Current Word

Cursor on word:

```vim
*
```

Next occurrence.

```vim
#
```

Previous occurrence.

---

# 7. Editing

## Delete Character

```vim
x
```

---

## Delete Word

```vim
dw
```

---

## Delete Line

```vim
dd
```

---

## Delete Multiple Lines

```vim
5dd
```

Deletes 5 lines.

---

## Change Word

```vim
ciw
```

Change Inner Word.

Very useful during development.

Example:

```java
private String username;
```

Cursor on username:

```vim
ciw
```

Type replacement.

---

# 8. Undo And Redo

Undo:

```vim
u
```

Redo:

```vim
Ctrl-r
```

---

# 9. Copy And Paste

## Copy Line

```vim
yy
```

---

## Copy Multiple Lines

```vim
5yy
```

---

## Paste Below

```vim
p
```

---

## Paste Above

```vim
P
```

---

# 10. Visual Mode Operations

Select:

```vim
V
```

Then:

```vim
d
```

Delete.

```vim
y
```

Copy.

```vim
>
```

Indent.

```vim
<
```

Unindent.

---

# 11. Buffers

A buffer is an opened file.

## List Buffers

```vim
:buffers
```

---

## Next Buffer

```vim
:bnext
```

---

## Previous Buffer

```vim
:bprev
```

---

## Delete Buffer

```vim
:bd
```

---

# 12. Windows

## Horizontal Split

```vim
:split
```

---

## Vertical Split

```vim
:vsplit
```

---

## Move Between Windows

```vim
Ctrl-w h
Ctrl-w j
Ctrl-w k
Ctrl-w l
```

---

## Close Window

```vim
:q
```

---

# 13. Tabs

## New Tab

```vim
:tabnew
```

---

## Next Tab

```vim
gt
```

---

## Previous Tab

```vim
gT
```

---

## Close Tab

```vim
:tabclose
```

---

# 14. Registers

Registers act as Neovim clipboards.

## View Registers

```vim
:reg
```

---

## Copy Into Register

```vim
"ayy
```

Store line in register a.

---

## Paste Register

```vim
"ap
```

---

# 15. Macros

One of the most powerful Neovim features.

## Start Recording

```vim
qa
```

Record into register a.

---

## Stop Recording

```vim
q
```

---

## Execute Macro

```vim
@a
```

---

## Execute Multiple Times

```vim
10@a
```

Runs 10 times.

---

# 16. Marks

## Create Mark

```vim
ma
```

Creates mark a.

---

## Jump To Mark

```vim
'a
```

---

# 17. Search And Replace

Current file:

```vim
:%s/old/new/g
```

---

Current line:

```vim
:s/old/new/g
```

---

Confirm every replacement:

```vim
:%s/old/new/gc
```

---

# 18. Useful Commands For Java Developers

## Format File

Usually through LSP:

```vim
:lua vim.lsp.buf.format()
```

---

## Organize Imports

Usually exposed through:

```vim
<leader>ca
```

Code Action.

---

## Go To Definition

```vim
gd
```

---

## Find References

```vim
gr
```

---

## Hover Documentation

```vim
K
```

---

## Rename Symbol

```vim
<leader>cr
```

---

# 19. Essential Daily Commands

```vim
gg
G
dd
yy
p
u
Ctrl-r
*
#
/text
n
N
ciw
:d
:w
:q
```

If mastered, these commands cover more than 80% of daily editing activity.

---

# 20. Best Practices

1. Stay in Normal Mode as much as possible.
2. Use motions instead of arrows.
3. Learn text objects (`ciw`, `diw`, `yiw`).
4. Prefer search over scrolling.
5. Use macros for repetitive work.
6. Learn buffer navigation early.
7. Keep hands on the keyboard.
8. Use splits instead of opening multiple editor windows.
9. Build muscle memory gradually.
10. Practice every day.

---

# Chapter Summary

After finishing this chapter you should be comfortable with:

- Navigation
- Editing
- Searching
- Registers
- Macros
- Buffers
- Windows
- Tabs
- Marks
- Search & Replace

These fundamentals are prerequisites for all future chapters:

- LazyVim
- JDTLS
- Java Development
- TestNG
- DAP
- Robot Framework
- Automation Engineering Workflows

---

# 21. Practical Java Examples

## Exercise 1 - Fast Navigation Inside a Java Class

Given:

```java
public class LoginPage {

    private String username;

    private String password;

    public void login(String username,
                      String password) {

        this.username = username;
        this.password = password;
    }

    public boolean isLogged() {
        return true;
    }

}
```

### Tasks

Navigate without arrows:

1. Go to class declaration.
2. Go to end of file.
3. Return to line containing `login`.
4. Search for `password`.
5. Move to next occurrence.
6. Move to previous occurrence.

### Expected Commands

```vim
gg
G
/login
n
N
```

---

## Exercise 2 - Rename Variable

Given:

```java
private String username;
```

Change to:

```java
private String email;
```

### Solution

Position the cursor on:

```java
username
```

Execute:

```vim
ciw
```

Type:

```java
email
```

Press:

```vim
Esc
```

---

## Exercise 3 - Delete Multiple Methods

Given:

```java
public void method1() {}

public void method2() {}

public void method3() {}

public void method4() {}
```

Delete methods 2 and 3.

### Solution

Navigate to method 2:

```vim
2dd
```

Or use Visual Line Mode:

```vim
Vj
d
```

---

# 22. Practical TestNG Examples

## Example - Navigate to a Test Method

Given:

```java
@Test
public void testUserLogin() {

}
```

Search:

```vim
/testUserLogin
```

Search all annotations:

```vim
/@Test
```

Move to next result:

```vim
n
```

Move to previous result:

```vim
N
```

---

## Exercise 4 - Find All Tests In A Class

Given:

```java
@Test
public void loginTest() {}

@Test
public void logoutTest() {}

@Test
public void createDocumentTest() {}
```

Find all test methods using only search.

### Suggested Solution

```vim
/@Test
```

Navigate through the results:

```vim
n
```

---

# 23. Practical Selenide Examples

## Example - Edit Locator Quickly

Given:

```java
private static final SelenideElement BTN_SAVE =
    $(By.id("save-button"));
```

Change:

```java
save-button
```

to:

```java
save-document-button
```

### Fastest Solution

Position the cursor on:

```java
save-button
```

Execute:

```vim
ci"
```

Type:

```java
save-document-button
```

Press:

```vim
Esc
```

---

## Exercise 5 - Replace All Locators

Replace:

```java
By.id(
```

with:

```java
By.xpath(
```

### Solution

```vim
:%s/By.id/By.xpath/g
```

---

# 24. Macro Exercises

## Example

Given:

```java
private String value1;
private String value2;
private String value3;
private String value4;
```

Transform into:

```java
private final String value1;
private final String value2;
private final String value3;
private final String value4;
```

### Record Macro

Start recording:

```vim
qa
```

Insert:

```java
final
```

Stop recording:

```vim
q
```

Run the macro:

```vim
3@a
```

---

# 25. Real Automation Examples

## Example 1 - Jump Between Page Object Methods

Search:

```vim
/goToDetailsOfImportantInformationPage
```

Move to next occurrence:

```vim
n
```

---

## Example 2 - Find Assertions

Search:

```vim
/assertEquals
```

---

## Example 3 - Find Locators

Search:

```vim
/SelenideElement
```

---

## Example 4 - Find All ElementsCollection Definitions

Search:

```vim
/ElementsCollection
```

Example:

```java
protected static final ElementsCollection DOCUMENT_ROWS =
    $$("tr.documentRow");
```

---

## Example 5 - Find Every @FindBy Annotation

Search:

```vim
/@FindBy
```

Move between results:

```vim
n
```

```vim
N
```

---

# 26. Daily Practice Challenge

Complete all tasks without touching the arrow keys.

## Task 1

Open:

```bash
nvim LoginPage.java
```

Navigate to:

- Class declaration
- Last method
- Specific variable

### Commands

```vim
gg
G
/search
```

---

## Task 2

Duplicate a Line

### Solution

```vim
yyp
```

---

## Task 3

Delete a Whole Method

### Solution

Navigate to beginning of method:

```vim
V
%
d
```

---

## Task 4

Replace:

```java
Thread.sleep(...)
```

with:

```java
shouldBe(Condition.visible)
```

### Solution

```vim
:%s/Thread.sleep(.*)/shouldBe(Condition.visible)/g
```

---

## Task 5

Find All TestNG Tests in a Project

Using Telescope:

```vim
:Telescope live_grep
```

Search:

```text
@Test
```

---

## Task 6

Open Definition of a Method

Position cursor on:

```java
goToDetailsOfMainRecipient()
```

Execute:

```vim
gd
```

Return:

```vim
Ctrl-o
```

---

# 27. Self Assessment

You should be able to perform all operations below without thinking.

## Navigation

```vim
gg
G
w
b
e
0
$
```

✅

---

## Search

```vim
*
#
/pattern
n
N
```

✅

---

## Editing

```vim
dd
yy
p
u
Ctrl-r
```

✅

---

## Java Development

```vim
gd
gr
K
```

✅

---

## Refactoring

```vim
ciw
diw
yiw
```

✅

---

## Productivity

```vim
qa
@a
```

✅

---

# Chapter 1 Mastery Checklist

Before proceeding to Chapter 2, verify you can:

- [ ] Navigate a Java class without arrow keys.
- [ ] Find every `@Test` method in a file.
- [ ] Rename variables with `ciw`.
- [ ] Rename method parameters with `ciw`.
- [ ] Create and execute macros.
- [ ] Navigate buffers.
- [ ] Navigate windows.
- [ ] Use registers.
- [ ] Use visual mode efficiently.
- [ ] Search and replace across a file.
- [ ] Use Telescope to locate files.
- [ ] Jump to Java definitions with `gd`.
- [ ] Return from definitions with `Ctrl-o`.
- [ ] Work comfortably in Normal Mode 90% of the time.

---

# Practical Challenge - ContentManagementTest

Using the following file:

```java
public class ContentManagementTest extends BaseTest {
```

Complete the following tasks:

### Challenge 1

Find:

```java
testAddNewImportantInformationEntry
```

### Solution

```vim
/testAddNewImportantInformationEntry
```

---

### Challenge 2

Find every test that contains:

```java
ImportantInformation
```

### Solution

```vim
/ImportantInformation
```

---

### Challenge 3

Rename:

```java
actualValuesHBDetails
```

across the entire file.

### Solution

```vim
:%s/actualValuesHBDetails/actualValuesImportantInformation/g
```

---

### Challenge 4

List all methods annotated with:

```java
@Test
```

### Solution

```vim
/@Test
```

Navigate:

```vim
n
```

---

### Challenge 5

Jump to:

```java
goToDetailsOfImportantInformationPage
```

definition.

### Solution

```vim
gd
```

---

# Next Chapter

Continue with:

```markdown
# Chapter 2 - Navigation Advanced
```

In the next chapter we will cover:

- Text Objects
- Advanced Motions
- Telescope
- Harpoon
- Quickfix Lists
- Project Navigation
- Java Refactoring Workflows
- Real Automation Examples using TestNG and Selenide

#chapter-2---navigation-advanced

# Chapter 2 - Navigation Advanced

#table-of-contents

---

# 1. Introduction

The goal of this chapter is to stop thinking in terms of:

```text
Character navigation
```

and start thinking in terms of:

```text
Code structure navigation
```

A senior Neovim user rarely moves one character at a time.

Instead, they navigate:

- Words
- Parameters
- Statements
- Methods
- Classes
- Blocks
- Test Cases
- XML Tags
- Locators
- Assertions

This significantly increases productivity in Java Automation projects.

---

# 2. Text Objects

Text Objects are one of Neovim's most powerful features.

Instead of selecting characters manually, Neovim understands:

```text
Words
Quotes
Methods
Blocks
Parameters
Tags
```

---

# 3. Inner Word (iw)

Given:

```java
private String username;
```

Cursor anywhere on:

```java
username
```

Delete word:

```vim
diw
```

Result:

```java
private String ;
```

---

### Change Word

```vim
ciw
```

Type:

```java
email
```

Result:

```java
private String email;
```

---

### Copy Word

```vim
yiw
```

---

# 4. Around Word (aw)

Given:

```java
private String username;
```

Delete including surrounding space:

```vim
daw
```

Result cleaner than:

```vim
diw
```

---

# 5. Inner Quotes

Given:

```java
String locator = "save-button";
```

Cursor inside:

```java
"save-button"
```

---

### Change Text

```vim
ci"
```

Type:

```java
save-document-button
```

Result:

```java
String locator = "save-document-button";
```

---

### Delete Content

```vim
di"
```

Result:

```java
String locator = "";
```

---

# 6. Inner Parentheses

Given:

```java
assertEquals(expectedValue, actualValue);
```

Delete arguments:

```vim
di(
```

Result:

```java
assertEquals();
```

---

Change arguments:

```vim
ci(
```

Type:

```java
newExpected, newActual
```

---

# 7. Inner Curly Braces

Given:

```java
public void login() {

    click(BTN_LOGIN);

    enterUsername();

    enterPassword();

}
```

Delete method body:

```vim
di{
```

Result:

```java
public void login() {

}
```

---

# 8. Percent Matching (%)

Very important for Java development.

Given:

```java
if(condition) {

}
```

Cursor:

```java
(
```

Jump:

```vim
%
```

Moves to:

```java
)
```

Execute again:

```vim
%
```

Returns.

Works with:

```text
()
{}
[]
<>
```

---

# 9. Find Character (f)

Given:

```java
public void login(String username)
```

Jump to:

```java
(
```

Execute:

```vim
f(
```

---

Jump to:

```java
u
```

```vim
fu
```

---

# 10. Till Character (t)

Given:

```java
public void login(String username)
```

Move just before:

```java
(
```

```vim
t(
```

Useful for editing method names.

---

# 11. Repeating Motions

Repeat last:

```vim
;
```

Repeat opposite direction:

```vim
,
```

Example:

```vim
fa
;
;
;
```

---

# 12. Advanced Searching

Search class:

```vim
/public class
```

---

Search methods:

```vim
/public void
```

---

Search tests:

```vim
/@Test
```

---

Search assertions:

```vim
/assertEquals
```

---

Search locators:

```vim
/SelenideElement
```

---

# 13. Search Results List

Current file:

```vim
:vimgrep /@Test/ %
```

Open results:

```vim
:copen
```

Move next:

```vim
:cnext
```

Move previous:

```vim
:cprev
```

---

# 14. Quickfix Window

Quickfix becomes essential when debugging large TestNG suites.

Open:

```vim
:copen
```

Close:

```vim
:cclose
```

Navigate:

```vim
:cnext
:cprev
```

---

# 15. Telescope

Telescope is your primary project navigation tool.

---

## Search Files

```vim
:Telescope find_files
```

---

## Search Text

```vim
:Telescope live_grep
```

Example:

Search:

```text
goToDetailsOfMainRecipient
```

Finds:

```java
goToDetailsOfMainRecipient()
```

across the entire project.

---

## Open Recently Used Files

```vim
:Telescope oldfiles
```

---

## Search Buffers

```vim
:Telescope buffers
```

---

# 16. Practical Telescope Exercises

## Find all TestNG Tests

Open:

```vim
:Telescope live_grep
```

Search:

```text
@Test
```

---

## Find all Selenide Locators

Search:

```text
SelenideElement
```

---

## Find all ElementsCollections

Search:

```text
ElementsCollection
```

---

## Find all Assertions

Search:

```text
assertEquals
```

---

# 17. Harpoon

Harpoon allows fast navigation between files.

---

## Add Current File

```vim
<leader>a
```

or:

```lua
require("harpoon"):list():add()
```

---

## Open Harpoon Menu

```vim
<leader>h
```

---

## Jump Directly

```vim
<leader>1
<leader>2
<leader>3
<leader>4
```

---

# 18. Java Development Workflow

Example:

Working on:

```java
ContentManagementTest
```

Need:

```java
ContentManagementPage
```

Use:

```vim
gd
```

Jump to definition.

---

Return:

```vim
Ctrl-o
```

---

Jump again:

```vim
Ctrl-i
```

---

# 19. Practical Java Exercises

## Exercise 1

Given:

```java
public void goToDetailsOfImportantInformationPage() {

    waitForPageToLoad();

}
```

Delete body.

### Solution

```vim
di{
```

---

## Exercise 2

Given:

```java
assertEquals(expectedValue, actualValue);
```

Replace arguments.

### Solution

```vim
ci(
```

---

## Exercise 3

Given:

```java
private static final String USERNAME =
    "admin";
```

Replace string.

### Solution

```vim
ci"
```

---

# 20. Practical TestNG Exercises

Open:

```java
ContentManagementTest.java
```

---

### Find all tests

```vim
/@Test
```

Navigate:

```vim
n
```

---

### Find specific test

```vim
/testEditAndSaveExistingImportantInformation
```

---

### Find all groups

```vim
/groups
```

---

# 21. Practical Selenide Exercises

Locate:

```java
SelenideElement BTN_SAVE
```

Jump:

```vim
/SelenideElement
```

---

Locate:

```java
ElementsCollection
```

Jump:

```vim
/ElementsCollection
```

---

Locate:

```java
By.xpath
```

Jump:

```vim
/By.xpath
```

---

# 22. Automation Navigation Challenge

Using:

```java
ContentManagementTest
```

Complete:

1. Find every `@Test`
2. Jump to `goToDetailsOfImportantInformationPage`
3. Return
4. Find `assertEquals`
5. List all results in Quickfix

### Commands

```vim
/@Test
gd
Ctrl-o
/assertEquals
:vimgrep /assertEquals/ %
:copen
```

---

# 23. Daily Efficiency Challenge

Without touching arrow keys:

### Challenge 1

Rename:

```java
mainRecipientName
```

everywhere in file.

Solution:

```vim
:%s/mainRecipientName/recipientName/g
```

---

### Challenge 2

Replace all:

```java
Thread.sleep
```

calls.

Solution:

```vim
:%s/Thread.sleep/shouldBe/g
```

---

### Challenge 3

Delete method body.

Solution:

```vim
di{
```

---

### Challenge 4

Replace string constant.

Solution:

```vim
ci"
```

---

# Chapter 2 Mastery Checklist

Before proceeding to Chapter 3, verify you can:

- [ ] Use `diw`
- [ ] Use `ciw`
- [ ] Use `di"`
- [ ] Use `ci"`
- [ ] Use `di(`
- [ ] Use `ci(`
- [ ] Use `di{`
- [ ] Use `%`
- [ ] Use `f`
- [ ] Use `t`
- [ ] Use Telescope
- [ ] Use Live Grep
- [ ] Use Quickfix
- [ ] Jump to definition (`gd`)
- [ ] Return (`Ctrl-o`)
- [ ] Navigate large Java projects without arrows

---

# Chapter Summary

After this chapter you should be able to navigate:

- Java classes
- TestNG suites
- Selenide Page Objects
- XML configurations
- Maven files

using structural navigation rather than character navigation.

This skill alone can reduce navigation time by more than 70% when working on large automation frameworks.

---

# Chapter 3 - LazyVim Configuration

#table-of-contents

---

# 1. Introduction

LazyVim is a preconfigured Neovim distribution focused on:

- Performance
- Modern UI
- Built-in LSP support
- DAP support
- Treesitter
- Telescope
- Git Integration
- Plugin Management

For Java Test Automation projects, LazyVim provides:

- Java Development
- Maven Support
- TestNG Development
- Robot Framework Development
- Selenide Development
- Debugging via DAP
- Terminal Integration

The purpose of this chapter is to understand the internal structure of LazyVim, allowing customization and troubleshooting.

---

# 2. LazyVim Directory Structure

Most important location:

```text
~/.config/nvim
```

Typical structure:

```text
~/.config/nvim
│
├── init.lua
│
├── lua
│   │
│   ├── config
│   │   ├── autocmds.lua
│   │   ├── keymaps.lua
│   │   ├── lazy.lua
│   │   └── options.lua
│   │
│   └── plugins
│       ├── java.lua
│       ├── dap.lua
│       ├── telescope.lua
│       └── custom.lua
│
├── lazy-lock.json
│
└── stylua.toml
```

---

# 3. Important Files

## init.lua

Entry point.

Loads the entire configuration.

Example:

```lua
require("config.lazy")
```

---

## options.lua

Editor options.

Example:

```lua
vim.opt.number = true
vim.opt.relativenumber = true
vim.opt.wrap = false
```

---

## keymaps.lua

Custom shortcuts.

Example:

```lua
vim.keymap.set(
  "n",
  "<leader>w",
  "<cmd>w<cr>",
  { desc = "Save file" }
)
```

---

## autocmds.lua

Automatic actions.

Example:

```lua
vim.api.nvim_create_autocmd(
  "BufWritePost",
  {
    pattern = "*.lua",
    callback = function()
      print("Saved")
    end
  }
)
```

---

## plugins/

Plugin customization.

Example:

```text
plugins
├── java.lua
├── dap.lua
├── telescope.lua
```

---

# 4. Understanding Plugin Loading

LazyVim uses:

```text
lazy.nvim
```

Plugin manager.

Benefits:

- Lazy loading
- Faster startup
- Dependency handling

---

Example:

```lua
return {
  {
    "mfussenegger/nvim-dap"
  }
}
```

---

# 5. Reloading Configuration

One of the most common activities.

---

## Reload Keymaps

File:

```text
lua/config/keymaps.lua
```

Reload:

```vim
:lua package.loaded["config.keymaps"] = nil
```

```vim
:lua require("config.keymaps")
```

---

Single line:

```vim
:lua package.loaded["config.keymaps"]=nil; require("config.keymaps")
```

---

## Reload Plugin Configuration

Example:

```lua
plugins/java.lua
```

Reload:

```vim
:Lazy reload
```

---

## Reload Everything

```vim
:source $MYVIMRC
```

Usually works for simple changes.

---

# 6. Verifying Keymaps

Very useful when debugging.

---

## List Current Mapping

Example:

```vim
:map <leader>tM
```

---

## Show Origin

```vim
:verbose map <leader>tM
```

Output example:

```text
Last set from:
~/.config/nvim/lua/config/keymaps.lua
```

This helps identify conflicts.

---

# 7. Creating Keymaps

Basic syntax:

```lua
vim.keymap.set(
  mode,
  key,
  action,
  options
)
```

---

Example:

```lua
vim.keymap.set(
  "n",
  "<leader>ff",
  "<cmd>Telescope find_files<cr>"
)
```

---

# 8. Practical Java Keymaps

## Run Current Maven Test

```lua
vim.keymap.set("n", "<leader>tm",
function()

  local class_name =
    vim.fn.expand("%:t:r")

  Snacks.terminal(
    "mvn test -Dtest=" .. class_name,
    {
      auto_close = false
    }
  )
end)
```

---

## Debug Current Test

```lua
vim.keymap.set("n", "<leader>td",
function()

  local class_name =
    vim.fn.expand("%:t:r")

  Snacks.terminal(
    "mvnDebug test -Dtest=" .. class_name,
    {
      auto_close = false
    }
  )
end)
```

---

# 9. Building TestNG Helpers

Example:

```lua
vim.keymap.set(
  "n",
  "<leader>tr",
  function()

    local class_name =
      vim.fn.expand("%:t:r")

    Snacks.terminal(
      "mvn test -Dtest="
      .. class_name,
      { auto_close = false }
    )
  end
)
```

---

# 10. Snacks Terminal

One of the most useful LazyVim plugins.

---

## Open Terminal

```lua
Snacks.terminal()
```

---

## Execute Command

```lua
Snacks.terminal(
  "mvn clean test"
)
```

---

## Persistent Terminal

```lua
Snacks.terminal(
  "mvnDebug test",
  {
    auto_close = false
  }
)
```

---

# 11. Bottom Debug Panel

Recommended approach.

Example:

```lua
Snacks.terminal(
  command,
  {
    auto_close = false,
    win = {
      position = "bottom",
      height = 15
    }
  }
)
```

Benefits:

- No popup blocking
- See logs
- Keep code visible
- Reusable terminal

---

# 12. Managing Plugins

Open:

```vim
:Lazy
```

---

Useful actions:

### Update Plugins

```vim
U
```

---

### Sync Plugins

```vim
:S
```

---

### Check Health

```vim
:checkhealth
```

---

# 13. Java Plugin Setup

Recommended packages:

```text
jdtls
java-debug-adapter
java-test
```

Installed through:

```vim
:Mason
```

---

# 14. Troubleshooting Java Setup

## Verify JDTLS

```vim
:LspInfo
```

Expect:

```text
Client: jdtls
```

---

## Verify Mason Packages

```vim
:Mason
```

Must contain:

```text
jdtls
java-debug-adapter
java-test
```

---

# 15. Common LazyVim Problems

## Keymap Does Not Work

Verify:

```vim
:verbose map
```

---

Reload:

```vim
:lua package.loaded["config.keymaps"]=nil
```

```vim
:lua require("config.keymaps")
```

---

## Plugin Not Loaded

Open:

```vim
:Lazy
```

Check:

```text
Loaded
Not Loaded
Disabled
```

---

## Unknown Command

Example:

```vim
:JavaTestDebugCurrentMethod
```

Missing.

Cause:

```text
java-test
not installed
```

---

# 16. Practical Exercises

## Exercise 1

Create:

```lua
<leader>ww
```

to save file.

Solution:

```lua
vim.keymap.set(
  "n",
  "<leader>ww",
  "<cmd>w<cr>"
)
```

---

## Exercise 2

Reload keymaps without restarting.

Solution:

```vim
:lua package.loaded["config.keymaps"]=nil
```

```vim
:lua require("config.keymaps")
```

---

## Exercise 3

Find where:

```text
<leader>tM
```

is defined.

Solution:

```vim
:verbose map <leader>tM
```

---

# 17. Real Automation Examples

## Maven Debug Method

```lua
Snacks.terminal(
  "mvnDebug test -Dtest="
  .. className
  .. "#"
  .. methodName,
  {
    auto_close = false,
  }
)
```

---

## ContentManagementTest

Run:

```bash
mvn test \
-Dtest=ContentManagementTest
```

through:

```lua
Snacks.terminal()
```

---

## Debug Specific TestNG Method

```bash
mvnDebug test \
-Dtest=ContentManagementTest#testEditAndSaveExistingImportantInformation
```

---

# 18. Daily Practice Challenge

Without using documentation:

1. Open `keymaps.lua`
2. Create a new mapping
3. Reload configuration
4. Verify mapping exists
5. Execute mapping
6. Remove mapping
7. Reload again

Commands required:

```vim
:w
```

```vim
:verbose map
```

```vim
:lua package.loaded["config.keymaps"]=nil
```

```vim
:lua require("config.keymaps")
```

---

# 19. Mastery Checklist

Before proceeding to Chapter 4:

- [ ] Understand LazyVim structure
- [ ] Edit keymaps.lua
- [ ] Edit options.lua
- [ ] Edit plugin files
- [ ] Reload keymaps
- [ ] Reload plugins
- [ ] Use Snacks terminal
- [ ] Create mappings
- [ ] Debug mappings
- [ ] Open Lazy dashboard
- [ ] Manage plugins
- [ ] Verify JDTLS
- [ ] Verify Mason packages

---

# Chapter Summary

After completing this chapter you should be able to:

- Configure LazyVim confidently.
- Debug your own keymaps.
- Create custom automation shortcuts.
- Launch Maven commands directly from Neovim.
- Use Snacks Terminal effectively.
- Manage Java-related plugins.
- Troubleshoot configuration problems quickly.

These skills are fundamental for the next chapter:

```markdown
# Chapter 4 - Java Development in Neovim
```

where we will cover:

- JDTLS
- Java Project Import
- Code Actions
- Refactoring
- Maven Integration
- Java Testing
- Java Debugging
- TestNG Workflows
- Advanced Productivity Workflows

# Chapter 4 - Java Development in Neovim

#table-of-contents

---

# 1. Introduction

The goal of this chapter is to transform Neovim into a fully-featured Java IDE capable of replacing IntelliJ IDEA for daily automation development.

By the end of this chapter you should be able to:

- Develop Java projects efficiently
- Navigate large codebases
- Execute Maven commands
- Refactor code
- Run TestNG tests
- Debug Java applications
- Debug TestNG methods
- Generate methods and constructors
- Organize imports
- Navigate implementations and references
- Work comfortably with Selenide Page Objects

---

# 2. Understanding JDTLS

JDTLS stands for:

```text
Java Development Tools Language Server
```

It provides:

- Autocomplete
- Refactoring
- Diagnostics
- Code Actions
- Go To Definition
- Hover Documentation
- Code Generation
- Symbol Search
- Java Debug Integration

---

# 3. Verifying JDTLS

Run:

```vim
:LspInfo
```

Expected:

```text
Client: jdtls
```

Example:

```text
Configured servers:
- jdtls

Attached clients:
- jdtls
```

---

# 4. Java Project Structure

Most automation frameworks follow:

```text
project
│
├── pom.xml
│
├── src
│   ├── main
│   │   └── java
│   │
│   └── test
│       └── java
│
├── suites
│
└── target
```

---

# 5. Working With Java Files

Open:

```vim
:Telescope find_files
```

Search:

```text
ContentManagementTest
```

---

Alternative:

```vim
:Telescope live_grep
```

Search:

```text
goToDetailsOfImportantInformationPage
```

---

# 6. Code Completion

Example:

```java
ArrayL
```

Press:

```vim
Ctrl-Space
```

or select completion through:

```vim
Tab
```

depending on your completion plugin.

---

# 7. Hover Documentation

Position cursor:

```java
ArrayList
```

Execute:

```vim
K
```

Example:

```java
List<String> users =
        new ArrayList<>();
```

Hover:

```vim
K
```

Shows:

```text
java.util.ArrayList
```

documentation.

---

# 8. Go To Definition

Given:

```java
contentManagementPage
    .goToDetailsOfImportantInformationPage();
```

Position cursor on:

```java
goToDetailsOfImportantInformationPage
```

Execute:

```vim
gd
```

Jumps to:

```java
public ImportantInformationDetailsPage
goToDetailsOfImportantInformationPage(...)
```

---

# 9. Returning From Definition

Return:

```vim
Ctrl-o
```

Forward:

```vim
Ctrl-i
```

---

# 10. Finding References

Position cursor:

```java
goToDetailsOfImportantInformationPage
```

Execute:

```vim
gr
```

Shows:

```text
All usages
```

through Telescope or Quickfix.

---

# 11. Workspace Symbol Search

Search class:

```vim
:Telescope lsp_workspace_symbols
```

Example:

```text
ContentManagementTest
```

---

Search method:

```text
clickEdit
```

---

# 12. Document Symbols

Current file symbols:

```vim
:Telescope lsp_document_symbols
```

Example:

```text
Methods
Variables
Inner Classes
```

Useful for large TestNG classes.

---

# 13. Java Refactoring

## Rename Symbol

Position cursor:

```java
mainRecipientName
```

Execute:

```vim
<leader>cr
```

Rename:

```java
recipientName
```

All references update automatically.

---

# 14. Organize Imports

Before:

```java
import java.util.List;
import java.util.ArrayList;
import java.util.HashMap;
```

Unused imports remain.

Execute:

```vim
<leader>ca
```

Select:

```text
Organize Imports
```

---

# 15. Code Actions

Execute:

```vim
<leader>ca
```

Common options:

```text
Generate Constructor
Generate Getter
Generate Setter
Generate Getters and Setters
Generate Equals and HashCode
Generate ToString
Override Methods
Implement Methods
Organize Imports
```

---

# 16. Generate Constructor

Given:

```java
public class User {

    private String username;
    private String password;

}
```

Execute:

```vim
<leader>ca
```

Choose:

```text
Generate Constructor
```

Generated:

```java
public User(
        String username,
        String password) {

    this.username = username;
    this.password = password;
}
```

---

# 17. Generate Getters And Setters

Execute:

```vim
<leader>ca
```

Choose:

```text
Generate Getters and Setters
```

Result:

```java
public String getUsername() {
    return username;
}

public void setUsername(
        String username) {

    this.username = username;
}
```

---

# 18. Override Method

Example:

```java
public class HBDetailsPage
        extends CMDetailsPage<HBDetailsPage> {
}
```

Execute:

```vim
<leader>ca
```

Select:

```text
Override Methods
```

Choose:

```text
getInstance()
```

Generated:

```java
@Override
public HBDetailsPage getInstance() {
    return this;
}
```

---

# 19. Implement Interface

Given:

```java
public class UserService
        implements IUserService {
}
```

Execute:

```vim
<leader>ca
```

Choose:

```text
Implement Methods
```

Generates missing methods.

---

# 20. Handling Multi-Step Code Actions

Sometimes:

```text
Override Method
```

opens another menu.

Navigation:

```vim
j
k
```

Select:

```vim
Enter
```

Mark multiple:

```vim
Space
```

Confirm:

```vim
Enter
```

This is particularly useful when overriding several TestNG listener methods.

---

# 21. Practical Java Example

Given:

```java
private String username;
private String password;
```

Task:

Generate:

```java
Constructor
Getter
Setter
toString
```

Solution:

```vim
<leader>ca
```

and select the appropriate actions.

---

# 22. Practical Selenide Example

Given:

```java
private static final SelenideElement BTN_SAVE =
    $(By.id("save"));
```

Navigate to:

```java
SelenideElement
```

Hover:

```vim
K
```

Jump:

```vim
gd
```

List usages:

```vim
gr
```

---

# 23. Practical TestNG Example

Given:

```java
@Test
public void testEditAndSaveExistingImportantInformation() {
}
```

Find all usages:

```vim
gr
```

Find symbol:

```vim
:Telescope lsp_document_symbols
```

---

# 24. Maven Integration

Run:

```bash
mvn clean test
```

Inside terminal:

```vim
<leader>ft
```

or

```lua
Snacks.terminal(
    "mvn clean test"
)
```

---

# 25. Working With pom.xml

Navigate profile:

```xml
<activeByDefault>true</activeByDefault>
```

Search:

```vim
/activeByDefault
```

---

Search profile:

```vim
/<profile>
```

---

# 26. Troubleshooting Java Development

## JDTLS Missing

Check:

```vim
:LspInfo
```

Expected:

```text
Client: jdtls
```

---

Install:

```vim
:Mason
```

Package:

```text
jdtls
```

---

## Code Actions Not Appearing

Verify:

```vim
<leader>ca
```

works.

Check:

```vim
:LspInfo
```

and verify:

```text
jdtls attached
```

---

## Go To Definition Not Working

Verify project imported correctly.

Check:

```vim
:LspInfo
```

and:

```vim
:Telescope lsp_workspace_symbols
```

---

## Imports Not Updating

Execute:

```vim
<leader>ca
```

Select:

```text
Organize Imports
```

---

# 27. Practical Challenge

Using:

```java
CMDetailsPage.java
```

Complete:

### Task 1

Find:

```java
getInstance
```

Solution:

```vim
/getInstance
```

---

### Task 2

Rename:

```java
mainRecipientName
```

using LSP rename.

Solution:

```vim
<leader>cr
```

---

### Task 3

Generate constructor for a new class.

Solution:

```vim
<leader>ca
```

---

### Task 4

Generate Getters and Setters.

Solution:

```vim
<leader>ca
```

---

### Task 5

Jump to definition and return.

Solution:

```vim
gd
Ctrl-o
```

---

# 28. Daily Practice Routine

Spend 10 minutes daily:

1. Navigate to definition
2. Rename variables
3. Generate constructors
4. Generate getters/setters
5. Use Telescope symbols
6. Organize imports
7. Use code actions

This builds Java navigation muscle memory quickly.

---

# Chapter 4 Mastery Checklist

Before proceeding to Chapter 5:

- [ ] Verify JDTLS
- [ ] Use Hover Documentation
- [ ] Use Go To Definition
- [ ] Use Find References
- [ ] Use Workspace Symbols
- [ ] Use Document Symbols
- [ ] Rename Variables
- [ ] Generate Constructors
- [ ] Generate Getters
- [ ] Generate Setters
- [ ] Override Methods
- [ ] Implement Interfaces
- [ ] Organize Imports
- [ ] Run Maven Commands
- [ ] Navigate Large Java Projects

---

# Chapter Summary

After this chapter you should be able to use Neovim as a full Java IDE.

You can now:

- Navigate large automation frameworks
- Refactor Java code
- Generate boilerplate automatically
- Work efficiently with TestNG
- Work efficiently with Selenide Page Objects
- Manage Maven projects

The next chapter focuses on:

```markdown
# Chapter 5 - TestNG Architecture
```

where we will cover:

- TestNG annotations
- Group strategy
- XML suites
- Parallel execution
- Listeners
- Retry analyzers
- Test architecture patterns
- Real examples from automation frameworks

# Chapter 5 - TestNG Architecture

#table-of-contents

---

# 1. Introduction

TestNG is one of the most popular Java testing frameworks used for:

- Unit Testing
- Integration Testing
- UI Testing
- API Testing
- Performance Testing Integration
- Automation Framework Design

In Enterprise Automation projects, TestNG is valued because it supports:

- Test Grouping
- Suite Execution
- Parallel Execution
- Dependency Management
- Data Providers
- Retry Mechanisms
- Listeners
- Reporting

This chapter focuses on practical usage for large automation frameworks such as Content Management, Document Management, Security Testing, and Selenide-Based UI Testing.

---

# 2. TestNG Execution Flow

Typical flow:

```text
Suite
 ├── Test
 │    ├── Class
 │    │     ├── @BeforeMethod
 │    │     ├── @Test
 │    │     └── @AfterMethod
 │    │
 │    └── Class
 │
 └── Test
```

Execution hierarchy:

```text
@BeforeSuite
@BeforeTest
@BeforeClass
@BeforeMethod
@Test
@AfterMethod
@AfterClass
@AfterTest
@AfterSuite
```

---

# 3. Basic Test Structure

Example:

```java
public class LoginTest {

    @Test
    public void testLogin() {

    }
}
```

---

# 4. Test Descriptions

Use descriptions whenever possible.

Example:

```java
@Test(
    description = "Verify user login"
)
public void testLogin() {

}
```

Advantages:

- Better reports
- Easier debugging
- Easier maintenance

---

# 5. Test Groups

One of the most important TestNG features.

Example:

```java
@Test(
    groups = {
        SMOKE,
        PUBLISHER,
        CONTENT_MANAGEMENT
    }
)
public void testPublishDocument() {

}
```

---

# 6. Recommended Group Strategy

For large automation projects:

```java
SMOKE
REGRESSION
SANITY
```

---

Business groups:

```java
CONTENT_MANAGEMENT
DOCUMENT_MANAGEMENT
USER_MANAGEMENT
```

---

User groups:

```java
CREATOR
PUBLISHER
VALIDATOR
ADMIN
```

---

Pipeline groups:

```java
EVERYDAY_RUN
NIGHTLY
WEEKLY
```

---

# 7. Example From Content Management

```java
@Test(
    description =
        "Add new entry for Content Management",
    groups = {
        CONTENT_MANAGEMENT,
        MAIN_WORKFLOWS,
        PUBLISHER,
        EVERYDAY_RUN
    }
)
public void testAddEntry() {

}
```

Benefits:

- Execute by role
- Execute by functionality
- Execute by pipeline

---

# 8. Running Groups

Run:

```bash
mvn test -Dgroups=SMOKE
```

---

Run multiple groups:

```bash
mvn test \
-Dgroups=SMOKE,PUBLISHER
```

---

Exclude groups:

```bash
mvn test \
-DexcludedGroups=FLAKY
```

---

# 9. BaseTest Pattern

Typical architecture:

```java
public class BaseTest {

    @BeforeMethod
    public void setup() {

    }

    @AfterMethod
    public void cleanup() {

    }
}
```

---

Feature test:

```java
public class ContentManagementTest
    extends BaseTest {

}
```

Benefits:

- Reusability
- Centralized setup
- Centralized cleanup

---

# 10. BeforeMethod

Runs before every test.

Example:

```java
@BeforeMethod
public void setup() {

    login();
}
```

---

Execution:

```text
Setup
Test 1

Setup
Test 2

Setup
Test 3
```

---

# 11. BeforeClass

Runs once.

Example:

```java
@BeforeClass
public void setupClass() {

}
```

Useful for:

- Large datasets
- Expensive initialization

---

# 12. BeforeSuite

Runs once before everything.

Example:

```java
@BeforeSuite
public void initializeEnvironment() {

}
```

---

Typical usage:

- Configuration
- Environment validation
- Global setup

---

# 13. Dependencies

Example:

```java
@Test
public void testCreateUser() {

}
```

```java
@Test(
    dependsOnMethods =
        "testCreateUser"
)
public void testEditUser() {

}
```

---

Execution:

```text
Create User
    ↓
Edit User
```

---

# 14. Priority

Example:

```java
@Test(priority = 1)
public void login() {

}
```

```java
@Test(priority = 2)
public void createDocument() {

}
```

---

Avoid excessive use.

Prefer:

```java
dependsOnMethods
```

when execution order matters.

---

# 15. Data Providers

Useful for repetitive tests.

Example:

```java
@DataProvider
public Object[][] users() {

    return new Object[][] {
        {"user1"},
        {"user2"},
        {"user3"}
    };
}
```

---

Usage:

```java
@Test(dataProvider = "users")
public void testLogin(
        String username) {

}
```

---

# 16. Retry Analyzer

Very common in UI Automation.

Example:

```java
@Test(
    retryAnalyzer = RetryAnalyzer.class
)
public void testSaveDocument() {

}
```

---

Implementation:

```java
public class RetryAnalyzer
        implements IRetryAnalyzer {

    @Override
    public boolean retry(
            ITestResult result) {

        return true;
    }
}
```

---

# 17. Why Retry Carefully

Good for:

```text
Browser crash
Network issue
Temporary UI instability
```

Bad for:

```text
Real defects
Consistent failures
```

---

Rule:

```text
Fix first.
Retry second.
```

---

# 18. Listeners

Listeners allow capturing events.

Example:

```java
public class TestListener
        implements ITestListener {

}
```

---

Events:

```java
onTestSuccess()
onTestFailure()
onTestSkipped()
onStart()
onFinish()
```

---

# 19. Screenshot On Failure

Example:

```java
@Override
public void onTestFailure(
        ITestResult result) {

    takeScreenshot();
}
```

Common Selenide implementation:

```java
Screenshots.takeScreenShotAsFile();
```

---

# 20. XML Suites

Simple suite:

```xml
<suite name="Smoke Suite">

    <test name="Smoke">

        <classes>

            <class
                name="Test.LoginTest"/>

        </classes>

    </test>

</suite>
```

---

# 21. Recommended XML Structure

```text
flows
├── creator
├── publisher
├── validator
├── smoke
├── regression
```

---

Example:

```text
publisher-smoke.xml
publisher-regression.xml
creator-smoke.xml
```

---

# 22. Parallel Execution

Enable:

```xml
<suite
    parallel="tests"
    thread-count="2">
```

---

Options:

```text
methods
classes
tests
instances
```

---

# 23. Real Parallel Example

```xml
<suite
    parallel="classes"
    thread-count="4">
```

Runs:

```text
LoginTest
ContentManagementTest
DocumentManagementTest
SecurityTest
```

simultaneously.

---

# 24. Risks Of Parallel Execution

Watch for:

```text
Shared users
Shared documents
Shared test data
```

---

Better:

```text
One user per thread
```

---

# 25. Practical Content Management Example

```java
@Test(
    groups = {
        CONTENT_MANAGEMENT,
        PUBLISHER,
        EVERYDAY_RUN
    }
)
public void
testAddNewImportantInformationEntry() {

}
```

Find all Content Management tests:

```vim
/CONTENT_MANAGEMENT
```

---

# 26. Practical XML Exercise

Create:

```text
publisher-smoke.xml
```

containing:

```java
ContentManagementTest
```

and

```java
DocumentManagementTest
```

Solution:

```xml
<suite>

    <test>

        <classes>

            <class
             name="tests.ContentManagementTest"/>

            <class
             name="tests.DocumentManagementTest"/>

        </classes>

    </test>

</suite>
```

---

# 27. Practical Challenge

Using:

```java
ContentManagementTest
```

Complete:

### Task 1

Find all:

```java
retryAnalyzer
```

Occurrences.

Solution:

```vim
/retryAnalyzer
```

---

### Task 2

Find all:

```java
groups =
```

Occurrences.

Solution:

```vim
/ groups =
```

---

### Task 3

List every:

```java
@Test
```

Solution:

```vim
/@Test
```

---

### Task 4

Run only one method:

```java
testAddNewImportantInformationEntry
```

Solution:

```bash
mvn test \
-Dtest=ContentManagementTest#testAddNewImportantInformationEntry
```

---

# 28. Daily Practice Routine

Every day:

1. Execute one method
2. Execute one class
3. Execute one XML suite
4. Execute one group
5. Run one retry scenario
6. Inspect reports
7. Review failures

---

# 29. Common TestNG Problems

## Tests Not Found

Verify:

```bash
mvn clean test
```

---

Check:

```java
@Test
```

Annotation exists.

---

## XML Not Working

Validate:

```xml
<class name="..."/>
```

Package is correct.

---

## Groups Not Executing

Verify:

```java
groups = {}
```

and

```bash
-Dgroups=
```

match.

---

## Retry Not Triggering

Verify:

```java
retryAnalyzer =
```

configured.

---

# 30. Mastery Checklist

Before proceeding to Chapter 6:

- [ ] Understand execution lifecycle
- [ ] Use groups
- [ ] Use dependencies
- [ ] Use priorities
- [ ] Create Data Providers
- [ ] Use Retry Analyzer
- [ ] Create Listeners
- [ ] Execute XML suites
- [ ] Execute groups
- [ ] Run single methods
- [ ] Configure parallel execution
- [ ] Understand parallel risks
- [ ] Troubleshoot TestNG failures

---

# Chapter Summary

After this chapter you should be able to:

- Design scalable TestNG frameworks
- Organize tests using groups
- Build maintainable suite structures
- Execute tests efficiently
- Debug failures quickly
- Support CI/CD pipelines

The next chapter:

```markdown
# Chapter 6 - Maven Workflows
```

will focus on:

- Maven lifecycle
- Surefire
- Failsafe
- Profiles
- Dependency Management
- Report Generation
- TestNG Integration
- Advanced Debug Workflows

# Chapter 6 - Maven Workflows

#table-of-contents

---

# 1. Introduction

Maven is the build tool responsible for:

- Dependency Management
- Compilation
- Testing
- Packaging
- Reporting
- CI/CD Integration

In Test Automation projects Maven usually manages:

```text
TestNG
Selenide
RestAssured
Allure
Robot Framework integrations
Locust support scripts
```

A solid understanding of Maven is essential for maintaining large automation frameworks.

---

# 2. Maven Lifecycle

The standard Maven lifecycle:

```text
validate
compile
test
package
verify
install
deploy
```

---

## Visual Flow

```text
validate
    ↓
compile
    ↓
test
    ↓
package
    ↓
verify
    ↓
install
    ↓
deploy
```

---

# 3. Most Important Maven Commands

## Compile

```bash
mvn compile
```

Compiles source code:

```text
src/main/java
```

---

## Test

```bash
mvn test
```

Runs:

```text
src/test/java
```

using Surefire.

---

## Clean

```bash
mvn clean
```

Deletes:

```text
target/
```

---

## Clean Test

```bash
mvn clean test
```

Most commonly used command.

---

## Install

```bash
mvn clean install
```

Compiles.

Executes tests.

Creates artifacts.

Installs in local repository.

---

# 4. Project Structure

Typical automation framework:

```text
project
│
├── pom.xml
│
├── src
│   ├── main
│   │   └── java
│   │
│   └── test
│       └── java
│
├── suites
│
├── payloads
│
└── target
```

---

# 5. Understanding pom.xml

The most important Maven file.

Example:

```xml
<project>

    <groupId>com.company</groupId>

    <artifactId>automation-framework</artifactId>

    <version>1.0.0</version>

</project>
```

---

# 6. Dependencies

Adding TestNG:

```xml
<dependency>

    <groupId>org.testng</groupId>

    <artifactId>testng</artifactId>

    <version>7.11.0</version>

</dependency>
```

---

Adding Selenide:

```xml
<dependency>

    <groupId>com.codeborne</groupId>

    <artifactId>selenide</artifactId>

    <version>7.7.3</version>

</dependency>
```

---

Adding RestAssured:

```xml
<dependency>

    <groupId>io.rest-assured</groupId>

    <artifactId>rest-assured</artifactId>

    <version>5.5.0</version>

</dependency>
```

---

# 7. Downloading Dependencies

Refresh all dependencies:

```bash
mvn dependency:resolve
```

---

Force update:

```bash
mvn clean install -U
```

Useful when snapshots become outdated.

---

# 8. Running a Single Class

Example:

```java
ContentManagementTest
```

Run:

```bash
mvn test \
-Dtest=ContentManagementTest
```

---

# 9. Running a Single Method

Example:

```java
testAddNewImportantInformationEntry
```

Run:

```bash
mvn test \
-Dtest=ContentManagementTest#testAddNewImportantInformationEntry
```

---

# 10. Running Multiple Methods

Example:

```bash
mvn test \
-Dtest=ContentManagementTest#testOne+testTwo
```

---

# 11. Executing By Groups

Example:

```java
SMOKE
```

Execute:

```bash
mvn test \
-Dgroups=SMOKE
```

---

Multiple groups:

```bash
mvn test \
-Dgroups=SMOKE,PUBLISHER
```

---

Exclude groups:

```bash
mvn test \
-DexcludedGroups=FLAKY
```

---

# 12. Executing XML Suites

Example:

```text
publisher-smoke.xml
```

Execution:

```bash
mvn test \
-DsuiteXmlFile=suites/publisher-smoke.xml
```

---

Multiple suites:

```bash
mvn test \
-DsuiteXmlFiles=suite1.xml,suite2.xml
```

---

# 13. Surefire Plugin

Main plugin responsible for TestNG execution.

Example:

```xml
<plugin>

    <groupId>
        org.apache.maven.plugins
    </groupId>

    <artifactId>
        maven-surefire-plugin
    </artifactId>

</plugin>
```

---

Used for:

```text
Unit Tests
UI Tests
API Tests
```

---

# 14. Surefire Reports

Generated:

```text
target/surefire-reports
```

Contains:

```text
XML Results
HTML Reports
Stacktraces
Failures
```

---

Useful command:

```bash
ls target/surefire-reports
```

---

# 15. Opening Surefire Results

Linux:

```bash
less target/surefire-reports/*.txt
```

---

Search failures:

```bash
grep -R "FAILED" \
target/surefire-reports
```

---

# 16. Failsafe Plugin

Used for:

```text
Integration Tests
Long Running Tests
```

Convention:

```text
*IT.java
```

Example:

```java
UserWorkflowIT.java
```

---

# 17. Maven Profiles

Profiles allow different configurations.

Example:

```xml
<profile>

    <id>publisher</id>

</profile>
```

---

Activate:

```bash
mvn test -Ppublisher
```

---

# 18. Default Profile

Example:

```xml
<activeByDefault>
    true
</activeByDefault>
```

If changed:

```xml
false -> true
```

No build required.

Just run Maven again.

---

# 19. Check Active Profiles

```bash
mvn help:active-profiles
```

---

Useful for debugging:

```text
Wrong Environment
Wrong User
Wrong Browser
```

---

# 20. Maven Properties

Example:

```xml
<properties>

    <browser>chrome</browser>

</properties>
```

Usage:

```bash
mvn test \
-Dbrowser=edge
```

---

# 21. Java + Neovim Workflow

Run class:

```lua
Snacks.terminal(
    "mvn test -Dtest="
    .. className
)
```

---

Run method:

```lua
Snacks.terminal(
    "mvn test -Dtest="
    .. className
    .. "#"
    .. methodName
)
```

---

# 22. Maven Debug Mode

Single method:

```bash
mvnDebug test \
-Dtest=ContentManagementTest#testEditAndSaveExistingImportantInformation
```

Output:

```text
Listening for transport dt_socket
at address: 8000
```

---

# 23. Attaching DAP

Start Maven:

```bash
mvnDebug test ...
```

Then:

```lua
require("dap").continue()
```

Attach:

```text
localhost:8000
```

---

# 24. Real Debug Workflow

Step 1:

```bash
mvnDebug test \
-Dtest=ContentManagementTest#testEditAndSaveExistingImportantInformation
```

---

Step 2:

Set breakpoint.

```vim
F9
```

---

Step 3:

Attach DAP.

```vim
F5
```

---

Step 4:

Inspect:

```java
expectedValuesHBDetails
actualValuesHBDetails
```

---

# 25. Cleaning Corrupted Builds

Sometimes Maven caches become inconsistent.

---

Clean:

```bash
mvn clean
```

---

Rebuild:

```bash
mvn clean install
```

---

Force dependency update:

```bash
mvn clean install -U
```

---

# 26. Practical Exercises

## Exercise 1

Run:

```java
ContentManagementTest
```

Solution:

```bash
mvn test \
-Dtest=ContentManagementTest
```

---

## Exercise 2

Run:

```java
testValidateRulesForCMImportantInformation
```

Solution:

```bash
mvn test \
-Dtest=ContentManagementTest#testValidateRulesForCMImportantInformation
```

---

## Exercise 3

Execute:

```java
SMOKE
```

group.

Solution:

```bash
mvn test \
-Dgroups=SMOKE
```

---

# 27. Practical Challenge

Using your framework:

### Task 1

Run:

```java
Publisher Smoke
```

suite.

---

### Task 2

Debug:

```java
testRegisteredUserMustAcceptTheUpdatedPrivacyStatementOnSubsequentLogin
```

---

### Task 3

Find Surefire report.

---

### Task 4

Identify active profile.

---

### Solutions

```bash
mvn test \
-DsuiteXmlFile=suites/publisher-smoke.xml
```

```bash
mvnDebug test \
-Dtest=ContentManagementTest#testRegisteredUserMustAcceptTheUpdatedPrivacyStatementOnSubsequentLogin
```

```bash
ls target/surefire-reports
```

```bash
mvn help:active-profiles
```

---

# 28. Common Maven Problems

## Dependency Not Found

```bash
mvn clean install -U
```

---

## Tests Not Executing

Verify:

```java
@Test
```

exists.

---

Verify:

```xml
maven-surefire-plugin
```

configured.

---

## XML Not Found

Verify path:

```bash
-DsuiteXmlFile=
```

---

## Wrong Profile

```bash
mvn help:active-profiles
```

---

## Target Folder Corrupted

Delete:

```bash
rm -rf target
```

Then:

```bash
mvn clean install
```

---

# 29. Daily Maven Routine

Every day:

1. Run single test.
2. Run single class.
3. Run XML suite.
4. Check active profiles.
5. Inspect Surefire reports.
6. Debug one test.
7. Verify Maven dependencies.

---

# 30. Mastery Checklist

Before proceeding to Chapter 7:

- [ ] Understand Maven lifecycle
- [ ] Use mvn test
- [ ] Use mvn clean install
- [ ] Run single methods
- [ ] Run single classes
- [ ] Run groups
- [ ] Run XML suites
- [ ] Understand Surefire
- [ ] Understand Failsafe
- [ ] Use profiles
- [ ] Debug with mvnDebug
- [ ] Attach DAP
- [ ] Read reports
- [ ] Troubleshoot Maven failures

---

# Chapter Summary

After this chapter you should be able to:

- Manage Maven projects confidently
- Execute TestNG tests efficiently
- Use profiles correctly
- Debug tests through Maven
- Analyze test results
- Troubleshoot common Maven issues

The next chapter:

```markdown
# Chapter 7 - DAP and nvim-dap
```

will cover:

- DAP Architecture
- Breakpoints
- Watches
- Variable Inspection
- Java Attach
- Conditional Breakpoints
- Debugging TestNG
- Advanced Debug Workflows
- Troubleshooting DAP

# Chapter 7 - DAP and nvim-dap

#table-of-contents

---

# 1. Introduction

DAP stands for:

```text
Debug Adapter Protocol
```

It was created by Microsoft to provide a common debugging protocol across different languages.

In Neovim, DAP provides functionality similar to:

- IntelliJ IDEA Debugger
- VS Code Debugger
- Eclipse Debugger

For Java Automation Engineers, DAP is one of the most powerful productivity tools available.

It enables:

- Breakpoints
- Variable inspection
- Call stack analysis
- Watch expressions
- Conditional breakpoints
- Remote JVM debugging
- TestNG debugging
- Maven attach debugging

---

# 2. DAP Architecture

Debugging generally follows this flow:

```text
Neovim
   ↓
nvim-dap
   ↓
Java Debug Adapter
   ↓
JVM
   ↓
Application/Test
```

---

## Java Workflow

```text
ContentManagementTest
       ↓
JDTLS
       ↓
Java Debug Adapter
       ↓
nvim-dap
       ↓
Neovim
```

---

# 3. Required Components

For Java Development:

```text
jdtls
java-debug-adapter
java-test
nvim-dap
nvim-dap-ui
```

Verify:

```vim
:Mason
```

Expected:

```text
Installed
----------
jdtls
java-debug-adapter
java-test
```

---

# 4. Verify DAP Installation

Run:

```vim
:lua print(vim.inspect(require("dap")))
```

Expected:

```text
table: 0x...
```

No errors should appear.

---

# 5. Understanding Debug Sessions

A session starts when:

```text
Application launches
```

or:

```text
Debugger attaches
```

and ends when:

```text
Program exits
```

or:

```text
Debugger terminates
```

---

# 6. Breakpoints

The most important debugging feature.

---

## Toggle Breakpoint

```lua
require("dap").toggle_breakpoint()
```

---

Typical keymap:

```lua
vim.keymap.set(
    "n",
    "<F9>",
    require("dap").toggle_breakpoint
)
```

---

Visual indicator:

```text
●
```

appears in the sign column.

---

# 7. Setting Breakpoints

Example:

```java
contentManagementPage
    .goToDetailsOfImportantInformationPage(null)
    .clickEdit();
```

Place cursor:

```java
.goToDetailsOfImportantInformationPage(null)
```

Press:

```vim
F9
```

Breakpoint added.

---

# 8. Continue Execution

Resume execution:

```lua
require("dap").continue()
```

---

Keymap:

```lua
vim.keymap.set(
    "n",
    "<F5>",
    require("dap").continue
)
```

---

# 9. Step Over

Execute current line without entering method.

```lua
require("dap").step_over()
```

---

Keymap:

```vim
F10
```

---

Example:

```java
loginPage.login();
```

Debugger executes line.

Does not enter:

```java
login()
```

implementation.

---

# 10. Step Into

Enter method.

```lua
require("dap").step_into()
```

---

Keymap:

```vim
F11
```

---

Example:

```java
loginPage.login();
```

Debugger enters:

```java
public void login() {
    ...
}
```

---

# 11. Step Out

Return to caller.

```lua
require("dap").step_out()
```

---

Keymap:

```vim
F12
```

---

# 12. Terminate Session

Stop debugging.

```lua
require("dap").terminate()
```

---

Keymap:

```lua
vim.keymap.set(
    "n",
    "<leader>dt",
    require("dap").terminate
)
```

---

# 13. DAP UI

Install:

```text
nvim-dap-ui
```

Provides:

- Variables
- Watches
- Breakpoints
- Call Stack
- Scopes

---

## Open UI

```lua
require("dapui").open()
```

---

## Close UI

```lua
require("dapui").close()
```

---

## Toggle UI

```lua
require("dapui").toggle()
```

---

# 14. Variables View

When debugger stops:

```java
String mainRecipientName;
```

Appears:

```text
Variables
 └── mainRecipientName
      └── value
```

Useful for:

```java
expectedValuesHBDetails
actualValuesHBDetails
```

during TestNG debugging.

---

# 15. Call Stack

Displays execution path.

Example:

```text
ContentManagementTest
 ↓
ContentManagementPage
 ↓
CMDetailsPage
 ↓
GenericMethods
```

Useful for investigating failures.

---

# 16. Watches

Track specific expressions.

Example:

```java
mainRecipientName
```

or:

```java
actualValuesHBDetails
```

Value updates while debugging.

---

# 17. Conditional Breakpoints

Very useful in loops.

Example:

```java
for(int i=0; i<100; i++) {
}
```

Break only:

```java
i == 50
```

---

Add:

```lua
require("dap")
    .set_breakpoint(
        "i == 50"
    )
```

---

# 18. Log Points

Print information without stopping.

Example:

```lua
require("dap")
.set_breakpoint(
    nil,
    nil,
    "Current value: {mainRecipientName}"
)
```

Useful when debugging collections.

---

# 19. Java DAP Configuration

Typical:

```lua
local dap = require("dap")

dap.configurations.java = {
    {
        type = "java",
        request = "attach",
        name = "Attach Maven Debug",
        hostName = "127.0.0.1",
        port = 8000
    }
}
```

---

# 20. Debug Current TestNG Method

If java-test configured:

```vim
:JavaTestDebugCurrentMethod
```

Cursor inside:

```java
@Test
public void testExample() {
}
```

---

DAP launches automatically.

---

# 21. Debug Current Test Class

```vim
:JavaTestDebugCurrentClass
```

---

Example:

```java
ContentManagementTest
```

---

# 22. Maven Attach Workflow

Start:

```bash
mvnDebug test \
-Dtest=ContentManagementTest#testEditAndSaveExistingImportantInformation
```

Maven waits:

```text
Listening for transport dt_socket
at address: 8000
```

---

Attach:

```lua
require("dap").continue()
```

Debugger connects.

---

# 23. Real Debugging Example

Suppose failure:

```java
expected:
John Smith

actual:
null
```

Breakpoint:

```java
String mrNameInDetails =
    getText(
        MAIN_RECIPIENT_NAME_VALUE
    );
```

Inspect:

```java
mainRecipientName
```

and:

```java
mrNameInDetails
```

before assertion.

---

# 24. Debugging Collections

Example:

```java
ElementsCollection rows =
    $$("tr");
```

Place breakpoint.

Inspect:

```java
rows.size()
```

and:

```java
rows.get(0)
```

through variables.

---

# 25. Debugging Generics

Example:

```java
public T getInstance() {
    return (T) this;
}
```

Breakpoint:

```java
return (T) this;
```

Inspect:

```java
this.getClass()
```

to verify actual type.

---

# 26. Debugging XML Suite Failures

Example:

```bash
mvnDebug test \
-DsuiteXmlFile=suites/publisher-smoke.xml
```

Breakpoint:

```java
@BeforeMethod
```

Verify:

```java
Current User
Environment
Profile
```

before tests start.

---

# 27. Common DAP Problems

## Breakpoint Not Hit

Verify:

```bash
mvn clean test
```

before debugging.

---

Check:

```text
Class being executed
=
Class being edited
```

---

## Attach Failure

Verify:

```bash
netstat -ano | grep 8000
```

Expected:

```text
Port open
```

---

## Variables Missing

Open:

```lua
require("dapui").open()
```

---

## DAP UI Not Showing

Verify:

```text
nvim-dap-ui
```

installed.

---

# 28. Practical Exercises

## Exercise 1

Add a breakpoint.

Solution:

```vim
F9
```

---

## Exercise 2

Continue execution.

Solution:

```vim
F5
```

---

## Exercise 3

Step into:

```java
login()
```

Solution:

```vim
F11
```

---

## Exercise 4

Terminate session.

Solution:

```vim
<leader>dt
```

or:

```lua
require("dap").terminate()
```

---

# 29. Practical Challenge

Using:

```java
ContentManagementTest
```

Perform:

### Task 1

Start:

```bash
mvnDebug
```

for:

```java
testEditAndSaveExistingImportantInformation
```

---

### Task 2

Attach DAP.

---

### Task 3

Breakpoint:

```java
clickEdit()
```

---

### Task 4

Inspect:

```java
expectedValuesHBDetails
```

---

### Task 5

Inspect:

```java
actualValuesHBDetails
```

---

### Task 6

Determine where values diverge.

---

# 30. Recommended Keymaps

```lua
local dap = require("dap")

vim.keymap.set(
    "n",
    "<F5>",
    dap.continue
)

vim.keymap.set(
    "n",
    "<F9>",
    dap.toggle_breakpoint
)

vim.keymap.set(
    "n",
    "<F10>",
    dap.step_over
)

vim.keymap.set(
    "n",
    "<F11>",
    dap.step_into
)

vim.keymap.set(
    "n",
    "<F12>",
    dap.step_out
)
```

---

# 31. Daily Practice Routine

Every day:

1. Debug one TestNG method.
2. Use one breakpoint.
3. Use one conditional breakpoint.
4. Inspect variables.
5. Navigate call stack.
6. Use DAP UI.
7. Debug one Selenide issue.

---

# 32. Mastery Checklist

Before proceeding to Chapter 8:

- [ ] Set breakpoints
- [ ] Remove breakpoints
- [ ] Continue execution
- [ ] Step Over
- [ ] Step Into
- [ ] Step Out
- [ ] Terminate sessions
- [ ] Attach to Maven
- [ ] Use DAP UI
- [ ] Inspect variables
- [ ] Inspect collections
- [ ] Use watches
- [ ] Use conditional breakpoints
- [ ] Debug TestNG methods
- [ ] Debug XML suites

---

# Chapter Summary

After this chapter you should be able to:

- Debug Java applications efficiently
- Debug TestNG tests
- Debug Selenide failures
- Attach to Maven debug sessions
- Analyze variables and call stacks
- Investigate framework issues quickly

The next chapter:

```markdown
# Chapter 8 - Maven Debug Attach
```

will focus on:

- Advanced Attach Workflows
- Debugging Suites
- Debugging Parallel Execution
- Remote JVM Debugging
- TestNG Debugging Strategies
- Real CI/CD Debugging
- JVM Debug Parameters
- Troubleshooting Attach Scenarios

# Chapter 8 - Maven Debug Attach

#table-of-contents

---

# 1. Introduction

One of the most powerful workflows for Java Test Automation is:

```text
Maven Debug
       +
DAP Attach
```

This approach allows:

- Debugging individual TestNG tests
- Debugging entire XML suites
- Debugging parallel executions
- Debugging Selenide Page Objects
- Debugging authentication flows
- Debugging framework initialization
- Debugging CI/CD issues

This is the closest experience to IntelliJ debugging while staying entirely inside Neovim.

---

# 2. Why Maven Debug Instead of JavaTestDebugCurrentMethod

Two debugging approaches exist:

## Direct JDTLS Debug

```vim
:JavaTestDebugCurrentMethod
```

Good for:

- Quick Tests
- Small Projects

---

## Maven Debug

```bash
mvnDebug test
```

Good for:

- Real Framework Execution
- Profiles
- XML Suites
- Parallel Execution
- CI/CD Reproduction
- Environment-Specific Bugs

---

# 3. How Maven Debug Works

Normal Flow:

```text
Neovim
 ↓
TestNG
 ↓
Execution
```

---

Debug Flow:

```text
Neovim
 ↓
DAP
 ↓
Attach
 ↓
JVM
 ↓
Maven
 ↓
TestNG
 ↓
Automation Framework
```

---

# 4. Maven Debug Command

Launch:

```bash
mvnDebug test
```

Output:

```text
Preparing to execute Maven in debug mode

Listening for transport dt_socket
at address: 8000
```

Maven is now paused.

Nothing executes until a debugger attaches.

---

# 5. Running One Test Method

Example:

```java
testEditAndSaveExistingImportantInformation
```

Launch:

```bash
mvnDebug test \
-Dtest=ContentManagementTest#testEditAndSaveExistingImportantInformation
```

---

# 6. Running One Test Class

Example:

```bash
mvnDebug test \
-Dtest=ContentManagementTest
```

---

# 7. Running XML Suites

Example:

```bash
mvnDebug test \
-DsuiteXmlFile=suites/publisher-smoke.xml
```

---

Framework executes exactly as CI/CD would.

---

# 8. Running Specific Groups

Example:

```bash
mvnDebug test \
-Dgroups=SMOKE
```

---

Multiple groups:

```bash
mvnDebug test \
-Dgroups=SMOKE,PUBLISHER
```

---

# 9. What Happens Internally

Maven launches JVM with:

```text
JDWP
(Java Debug Wire Protocol)
```

Equivalent:

```bash
-agentlib:jdwp=
```

Debugger waits:

```text
localhost:8000
```

---

# 10. DAP Attach Configuration

Example:

```lua
local dap = require("dap")

dap.configurations.java = {
    {
        type = "java",
        request = "attach",
        name = "Attach to Maven Debug",
        hostName = "127.0.0.1",
        port = 8000,
    }
}
```

---

# 11. Manual Attach

After:

```bash
mvnDebug test ...
```

execute:

```lua
require("dap").continue()
```

Debugger attaches.

---

# 12. Complete Workflow

Step 1

Run:

```bash
mvnDebug test \
-Dtest=ContentManagementTest#testAddNewImportantInformationEntry
```

---

Step 2

Set breakpoint:

```java
.addNewImportantInformationEntry()
```

---

Step 3

Attach:

```vim
F5
```

---

Step 4

Execution continues.

Stops on breakpoint.

---

# 13. Breakpoint Strategy

Avoid:

```java
@Test
public void testSomething() {

}
```

first line.

---

Instead use:

```java
pageObject
    .clickEdit();
```

or:

```java
assertEquals(
    expected,
    actual
);
```

or:

```java
return new HBDetailsPage();
```

---

# 14. Debugging Page Objects

Example:

```java
contentManagementPage
    .clickEdit()
    .save()
```

Breakpoint:

```java
clickEdit()
```

---

Inspect:

```java
this
```

Verify:

```java
Actual page type
```

---

# 15. Debugging Assertions

Example:

```java
assertEquals(
    expectedValues,
    actualValues
)
```

Breakpoint before assertion.

Inspect:

```java
expectedValues
```

and:

```java
actualValues
```

---

# 16. Debugging Generics

Example:

```java
public T getInstance() {
    return (T) this;
}
```

Breakpoint:

```java
return (T) this;
```

Inspect:

```java
this.getClass()
```

Verify:

```text
HBDetailsPage
LegalInformationDetailsPage
```

instead of:

```text
CMDetailsPage
```

---

# 17. Debugging Selenide Page Objects

Example:

```java
goToDetailsOfMainRecipient()
```

Breakpoint:

```java
row.getText()
```

Inspect:

```java
row
```

Verify:

```java
ElementsCollection
```

contains expected data.

---

# 18. Debugging ElementsCollection

Example:

```java
ElementsCollection rows =
        $$("tr");
```

Breakpoint:

```java
rows.size()
```

Inspect:

```java
rows
```

Open:

```java
rows[0]
rows[1]
rows[2]
```

---

# 19. Debugging Authentication

Example:

```java
AuthenticationCalls.login()
```

Breakpoint:

```java
response
```

Inspect:

```java
headers
cookies
statusCode
```

Very useful for SAML workflows.

---

# 20. Debugging TestNG Lifecycle

Breakpoint:

```java
@BeforeSuite
```

Verify:

```java
Environment
Browser
Profile
```

before tests run.

---

Breakpoint:

```java
@BeforeMethod
```

Verify:

```java
User
Language
Permissions
```

---

# 21. Debugging XML Suite Problems

Problem:

```text
Class not executing
```

Breakpoint:

```java
@BeforeClass
```

If not reached:

```text
XML configuration problem
```

---

# 22. Debugging Parallel Execution

Example:

```xml
parallel="tests"
thread-count="4"
```

Breakpoint:

```java
@BeforeMethod
```

Inspect:

```java
Thread.currentThread().getName()
```

---

Verify:

```text
Independent execution
```

---

# 23. Debugging User Collisions

Common issue:

```text
Two tests use same user.
```

Breakpoint:

```java
login()
```

Inspect:

```java
username
```

for every thread.

---

# 24. Debugging CI Failures Locally

Suppose:

```text
Works locally
Fails in pipeline
```

Reproduce:

```bash
mvnDebug test \
-Ppipeline
```

Attach DAP.

Compare:

```java
Configuration
Profile
Environment
```

---

# 25. Debugging RetryAnalyzer

Breakpoint:

```java
retry()
```

Inspect:

```java
result.getName()
```

Check:

```java
Retry count
```

---

# 26. JVM Debug Parameters

Equivalent debug configuration:

```bash
-agentlib:jdwp=
transport=dt_socket,
server=y,
suspend=y,
address=8000
```

Meaning:

```text
transport = socket
server = JVM listens
suspend = wait for debugger
address = port
```

---

# 27. Common Problems

## Cannot Attach

Check:

```bash
netstat -ano | grep 8000
```

Port must exist.

---

## Attach Disconnects

Test finished too quickly.

Add breakpoint earlier.

---

## Breakpoint Ignored

Verify:

```bash
mvn clean test
```

Fresh compilation.

---

## Wrong Source

Verify:

```text
Editing same module
being executed
```

---

# 28. Practical Exercise

Start:

```bash
mvnDebug test \
-Dtest=ContentManagementTest#testValidateRulesForCMImportantInformation
```

---

Add breakpoint:

```java
validateRules()
```

---

Attach DAP.

---

Inspect:

```java
title
```

and:

```java
pdf
```

values.

---

# 29. Practical Challenge

Debug:

```java
testRegisteredUserMustAcceptTheUpdatedPrivacyStatementOnSubsequentLogin
```

Tasks:

1. Launch Maven debug.
2. Attach DAP.
3. Stop before login.
4. Inspect user.
5. Inspect profile.
6. Step Into authentication.
7. Step Out.
8. Continue execution.
9. Verify assertion.

---

# 30. Productivity Workflows

## Workflow 1 - Single Method

```bash
mvnDebug test \
-Dtest=Class#method
```

Best for:

```text
Rapid Development
```

---

## Workflow 2 - Full Class

```bash
mvnDebug test \
-Dtest=ContentManagementTest
```

Best for:

```text
Feature Development
```

---

## Workflow 3 - XML Suite

```bash
mvnDebug test \
-DsuiteXmlFile=suites/publisher-smoke.xml
```

Best for:

```text
Release Validation
```

---

# 31. Daily Practice Routine

Every day:

1. Debug one method.
2. Debug one class.
3. Inspect a collection.
4. Inspect a Page Object.
5. Debug one failed assertion.
6. Debug one TestNG lifecycle method.

---

# 32. Mastery Checklist

Before proceeding to Chapter 9:

- [ ] Use mvnDebug
- [ ] Attach DAP
- [ ] Debug single methods
- [ ] Debug classes
- [ ] Debug XML suites
- [ ] Debug collections
- [ ] Debug Page Objects
- [ ] Debug assertions
- [ ] Debug RetryAnalyzer
- [ ] Debug BeforeMethod
- [ ] Debug BeforeSuite
- [ ] Debug parallel execution
- [ ] Troubleshoot attach failures

---

# Chapter Summary

After completing this chapter you should be able to:

- Attach Neovim to any Maven debug session
- Diagnose complex framework issues
- Debug TestNG suites efficiently
- Investigate Selenide failures
- Validate framework initialization
- Reproduce CI/CD problems locally

The next chapter:

```markdown
# Chapter 9 - Snacks Terminal
```

will cover:

- Terminal Architecture
- Persistent Terminals
- Reusable Debug Panels
- Maven Integration
- Java Integration
- TestNG Integration
- Log Monitoring
- Productivity Workflows

# Chapter 9 - Snacks Terminal

#table-of-contents

---

# 1. Introduction

Snacks Terminal is one of the most useful tools in a Java Automation workflow.

It allows you to:

- Execute Maven commands
- Run TestNG tests
- Launch Maven debug sessions
- Monitor logs
- Open multiple terminals
- Reuse terminals
- Keep Neovim focused on coding

Compared with:

```text
:terminal
```

Snacks provides:

```text
Better UX
Reusable terminals
Floating terminals
Split terminals
Persistent sessions
Better integration with LazyVim
```

---

# 2. Why Use Snacks Terminal

Typical Java workflow:

```text
Edit Code
 ↓
Open Terminal
 ↓
Run Maven
 ↓
Inspect Logs
 ↓
Debug
 ↓
Edit Code
```

Without Snacks:

```text
Constant window switching
```

With Snacks:

```text
Integrated workflow
```

---

# 3. Verify Snacks Installation

Open Lazy:

```vim
:Lazy
```

Search:

```text
snacks.nvim
```

Expected:

```text
Loaded
```

---

# 4. Open Terminal

Basic:

```lua
Snacks.terminal()
```

---

Equivalent command:

```vim
:lua Snacks.terminal()
```

---

# 5. Execute Commands

Example:

```lua
Snacks.terminal(
    "mvn clean test"
)
```

---

Result:

```text
Maven launches
Logs appear
Terminal remains available
```

---

# 6. Running Maven Tests

Example:

```lua
Snacks.terminal(
    "mvn test"
)
```

---

Useful for:

```text
Smoke runs
Regression runs
Quick validation
```

---

# 7. Running Specific Classes

Example:

```java
ContentManagementTest
```

Execute:

```lua
Snacks.terminal(
    "mvn test -Dtest=ContentManagementTest"
)
```

---

# 8. Running Specific Methods

Example:

```java
testAddNewImportantInformationEntry
```

Execute:

```lua
Snacks.terminal(
    "mvn test "
    .. "-Dtest=ContentManagementTest"
    .. "#testAddNewImportantInformationEntry"
)
```

---

# 9. Running XML Suites

Example:

```lua
Snacks.terminal(
    "mvn test "
    .. "-DsuiteXmlFile=suites/publisher-smoke.xml"
)
```

---

Useful for:

```text
Smoke
Regression
CI Reproduction
```

---

# 10. Maven Debug Sessions

Example:

```lua
Snacks.terminal(
    "mvnDebug test "
    .. "-Dtest=ContentManagementTest"
)
```

---

Output:

```text
Listening for transport dt_socket
at address: 8000
```

DAP can now attach.

---

# 11. Prevent Terminal Closing

Bad:

```lua
Snacks.terminal(
    command
)
```

May close automatically.

---

Better:

```lua
Snacks.terminal(
    command,
    {
        auto_close = false
    }
)
```

---

# 12. Floating Terminal

Example:

```lua
Snacks.terminal(
    "mvn clean test",
    {
        win = {
            position = "float"
        }
    }
)
```

---

Advantages:

```text
Compact
Temporary
Quick Commands
```

---

# 13. Split Terminal

Recommended for Java development.

Example:

```lua
Snacks.terminal(
    "mvn clean test",
    {
        win = {
            position = "bottom",
            height = 15
        }
    }
)
```

---

Advantages:

```text
See code and logs simultaneously
Ideal for Maven
Ideal for Debug
```

---

# 14. Why Bottom Split Is Better

Popup issues:

```text
Blocks screen
Harder to monitor logs
Can hide code
```

---

Bottom panel:

```text
Persistent
Visible
Non-intrusive
```

---

Recommended for:

```text
TestNG
Selenide
Maven Debug
```

---

# 15. Real Java Workflow

Editing:

```java
ContentManagementTest
```

---

Run:

```lua
Snacks.terminal(
    "mvn test "
    .. "-Dtest=ContentManagementTest"
)
```

---

Inspect:

```text
Failures
Warnings
Assertions
```

without leaving Neovim.

---

# 16. Building Custom Keymaps

Example:

```lua
vim.keymap.set(
    "n",
    "<leader>tm",
    function()
        Snacks.terminal(
            "mvn clean test",
            {
                auto_close = false
            }
        )
    end,
    {
        desc = "Maven Test"
    }
)
```

---

# 17. Running Current Class

Example:

```lua
vim.keymap.set(
    "n",
    "<leader>tc",
    function()

        local class_name =
            vim.fn.expand("%:t:r")

        Snacks.terminal(
            "mvn test -Dtest="
            .. class_name,
            {
                auto_close = false
            }
        )

    end
)
```

---

# 18. Running Current Method

Helper:

```lua
local method_name =
    get_java_method_name()
```

Run:

```lua
Snacks.terminal(
    "mvn test -Dtest="
    .. class_name
    .. "#"
    .. method_name,
    {
        auto_close = false
    }
)
```

---

# 19. Running Current Method In Debug

Example:

```lua
Snacks.terminal(
    "mvnDebug test -Dtest="
    .. class_name
    .. "#"
    .. method_name,
    {
        auto_close = false
    }
)
```

---

Workflow:

```text
Open Debug Terminal
 ↓
Maven waits
 ↓
Attach DAP
 ↓
Debug
```

---

# 20. Persisting Debug Terminals

Example:

```lua
local debug_term
```

---

Save reference:

```lua
debug_term =
    Snacks.terminal(
        command,
        {
            auto_close = false
        }
    )
```

---

Reuse later.

---

# 21. Closing Terminals

Example:

```lua
debug_term:close()
```

---

Keymap:

```lua
vim.keymap.set(
    "n",
    "<leader>tX",
    function()

        if debug_term then
            debug_term:close()
        end

    end
)
```

---

# 22. Monitoring Maven Logs

Example:

```text
BUILD SUCCESS
```

or:

```text
BUILD FAILURE
```

---

Useful sections:

```text
Failures
Errors
Skipped
Tests run
```

---

# 23. Monitoring Surefire Results

Show:

```text
Tests run: 347

Failures: 2

Errors: 1

Skipped: 4
```

Immediately visible.

---

# 24. Monitoring TestNG Execution

Example:

```text
Running ContentManagementTest

Running UserManagementTest

Running SecurityTest
```

Useful for:

```text
Parallel execution
```

---

# 25. Running Multiple Commands

Example:

```lua
Snacks.terminal(
    "mvn clean && mvn test"
)
```

---

Or:

```lua
Snacks.terminal(
    "mvn clean install"
)
```

---

# 26. Running Git Commands

Example:

```lua
Snacks.terminal(
    "git status"
)
```

---

Useful shortcuts:

```text
git status
git diff
git pull
git push
```

---

# 27. Running Robot Framework

Example:

```lua
Snacks.terminal(
    "robot tests"
)
```

---

# 28. Running Locust

Example:

```lua
Snacks.terminal(
    "locust"
)
```

---

# 29. Running Security Tools

Example:

```lua
Snacks.terminal(
    "zap.sh"
)
```

or:

```lua
Snacks.terminal(
    "burpsuite"
)
```

---

# 30. Practical Exercise

Create:

```lua
<leader>mt
```

Run:

```bash
mvn clean test
```

Solution:

```lua
vim.keymap.set(
    "n",
    "<leader>mt",
    function()

        Snacks.terminal(
            "mvn clean test",
            {
                auto_close = false
            }
        )

    end
)
```

---

# 31. Practical Challenge

Create a workflow that:

1. Finds current class.
2. Finds current method.
3. Launches:

```bash
mvnDebug test
```

4. Opens in bottom panel.
5. Keeps terminal open.

Expected:

```lua
Snacks.terminal(
    "mvnDebug test "
    .. "-Dtest="
    .. class_name
    .. "#"
    .. method_name,
    {
        auto_close = false,

        win = {
            position = "bottom",
            height = 15
        }
    }
)
```

---

# 32. Troubleshooting

## Terminal Opens Then Closes

Add:

```lua
auto_close = false
```

---

## Command Not Found

Verify:

```bash
which mvn
```

---

## Maven Uses Wrong Java

Verify:

```bash
java -version
```

---

## Nothing Happens

Try:

```vim
:checkhealth
```

Verify:

```text
snacks.nvim loaded
```

---

## Debug Terminal Closes

Disable:

```lua
auto_close
```

and keep:

```lua
false
```

---

# 33. Daily Practice Routine

Every day:

1. Run one class.
2. Run one method.
3. Run one XML suite.
4. Launch one debug session.
5. Inspect logs.
6. Close terminal.
7. Reopen terminal.

---

# 34. Mastery Checklist

Before proceeding to Chapter 10:

- [ ] Open terminal
- [ ] Run Maven
- [ ] Run TestNG classes
- [ ] Run TestNG methods
- [ ] Run XML suites
- [ ] Run Maven Debug
- [ ] Use bottom panels
- [ ] Use floating terminals
- [ ] Reuse terminals
- [ ] Close terminals programmatically
- [ ] Create custom keymaps
- [ ] Troubleshoot terminal issues

---

# Chapter Summary

After this chapter you should be able to:

- Run all automation workflows without leaving Neovim
- Launch Maven and TestNG commands quickly
- Start debug sessions from keymaps
- Monitor logs efficiently
- Build reusable development workflows
- Improve productivity significantly

The next chapter:

```markdown
# Chapter 10 - Selenide Best Practices
```

will cover:

- Page Object Design
- Selenide Conditions
- ElementsCollection
- Dynamic Locators
- Stable Selectors
- Wait Strategies
- Fluent APIs
- Framework Architecture
- Debugging Selenide Tests
- Real Automation Examples

# Chapter 10 - Selenide Best Practices

#table-of-contents

---

# 1. Introduction

Selenide is a wrapper around Selenium WebDriver designed to reduce boilerplate code and improve test maintainability.

Key advantages:

- Built-in waits
- Cleaner syntax
- Reduced flakiness
- Better assertions
- Automatic retries
- Faster development

For Test Automation frameworks, Selenide encourages:

```text
Readable Tests
Stable Locators
Lightweight Page Objects
Reusable Components
```

---

# 2. Why Selenide Instead Of Selenium

Traditional Selenium:

```java
driver.findElement(
    By.id("save")
).click();
```

---

Selenide:

```java
$("#save").click();
```

---

Traditional Selenium Wait:

```java
WebDriverWait wait =
    new WebDriverWait(
        driver,
        Duration.ofSeconds(10)
    );

wait.until(
    ExpectedConditions
        .visibilityOfElementLocated(...)
);
```

---

Selenide:

```java
$("#save")
    .shouldBe(Condition.visible)
    .click();
```

---

# 3. Core Concepts

Most commonly used classes:

```java
SelenideElement
ElementsCollection
Condition
Configuration
```

---

# 4. SelenideElement

Represents:

```text
One Element
```

Example:

```java
private static final SelenideElement
BTN_SAVE =
    $("#save");
```

---

Interaction:

```java
BTN_SAVE.click();
```

---

Input:

```java
INPUT_USER.setValue("admin");
```

---

Text:

```java
String value =
    BTN_SAVE.getText();
```

---

# 5. ElementsCollection

Represents:

```text
Multiple Elements
```

Example:

```java
ElementsCollection rows =
    $$("tr");
```

---

First element:

```java
rows.get(0);
```

---

Count:

```java
rows.size();
```

---

# 6. Prefer Collections Over Dynamic XPaths

Bad:

```java
$x("(//tr)[1]")
```

---

Better:

```java
$$("tr")
    .first();
```

---

Best:

```java
DOCUMENT_ROWS
    .first();
```

---

# 7. Conditions

Conditions are the heart of Selenide.

---

Visible:

```java
element.shouldBe(
    Condition.visible
);
```

---

Hidden:

```java
element.shouldBe(
    Condition.hidden
);
```

---

Exist:

```java
element.should(
    Condition.exist
);
```

---

Text:

```java
element.shouldHave(
    Condition.text("Success")
);
```

---

# 8. Never Use Thread.sleep()

Avoid:

```java
Thread.sleep(5000);
```

---

Use:

```java
BTN_SAVE.shouldBe(
    Condition.visible
);
```

or:

```java
LOADER.shouldDisappear();
```

---

# 9. Waiting Correctly

Bad:

```java
Thread.sleep(10000);
```

---

Good:

```java
TABLE.shouldBe(
    Condition.visible
);
```

---

Best:

```java
SUCCESS_MESSAGE
    .shouldHave(
        Condition.text(
            "Saved"
        )
    );
```

---

# 10. Stable Locators

Priority:

```text
data-testid
id
name
aria-label
class
xpath
```

---

Best:

```java
$("[data-testid='save']")
```

---

Good:

```java
$("#save")
```

---

Avoid:

```java
$("div > div > div > span")
```

---

# 11. XPath Best Practices

Bad:

```java
/html/body/div[1]/section/div[2]
```

---

Better:

```java
//button[text()='Save']
```

---

Best:

```java
//button[
 contains(@data-testid,'save')
]
```

---

# 12. Page Object Pattern

Recommended:

```java
LoginPage
ContentManagementPage
HBDetailsPage
```

Each page:

```text
Locators
Business actions
Validations
```

---

# 13. Good Page Object Example

```java
public class LoginPage {

    private final SelenideElement
        USERNAME =
            $("#username");

    private final SelenideElement
        PASSWORD =
            $("#password");

    private final SelenideElement
        BTN_LOGIN =
            $("#login");

}
```

---

# 14. Business Methods

Avoid:

```java
page.clickButton();
```

---

Prefer:

```java
page.login(
    username,
    password
);
```

Example:

```java
public HomePage login(
        String user,
        String pass) {

    USERNAME.setValue(user);

    PASSWORD.setValue(pass);

    BTN_LOGIN.click();

    return new HomePage();
}
```

---

# 15. Fluent APIs

Good:

```java
contentManagementPage
    .clickEdit()
    .save()
    .validate();
```

---

Avoid:

```java
clickEdit();

save();

validate();
```

---

# 16. Self-Validating Actions

Bad:

```java
BTN_SAVE.click();
```

---

Better:

```java
BTN_SAVE.click();

SUCCESS_MESSAGE.shouldBe(
    Condition.visible
);
```

---

# 17. Assertions

Prefer Selenide assertions:

```java
element.shouldHave(
    Condition.text(
        "Success"
    )
);
```

---

Instead of:

```java
assertEquals(
    "Success",
    element.getText()
);
```

---

# 18. Text Verification

Exact:

```java
Condition.exactText(
    "Entry successfully added"
)
```

---

Partial:

```java
Condition.text(
    "successfully"
)
```

---

# 19. Forms

Good:

```java
TITLE_INPUT.setValue(
    value
);
```

---

Clear:

```java
TITLE_INPUT.clear();
```

---

Append:

```java
TITLE_INPUT.append(
    "_updated"
);
```

---

# 20. ElementsCollection Usage

Example:

```java
ElementsCollection rows =
    $$("tr.document");
```

Find:

```java
rows.findBy(
    Condition.text(
        "Document"
    )
);
```

---

Filter:

```java
rows.filterBy(
    Condition.visible
);
```

---

# 21. Example From Main Recipient

Instead of:

```java
$x("(//tr)[1]")
```

Use:

```java
ElementsCollection rows =
    $$("tr.mainRecipientRow");
```

---

Search:

```java
rows.findBy(
    Condition.text(
        "John Smith"
    )
);
```

---

# 22. Dynamic Search Pattern

Example:

```java
rows.stream()
    .filter(...)
```

---

Better:

```java
rows.findBy(
    Condition.text(
        recipientName
    )
);
```

---

Readable.

Maintainable.

---

# 23. Common Framework Pattern

Page:

```java
goToDetails()
```

returns:

```java
DetailsPage
```

Example:

```java
public HBDetailsPage
goToDetails() {

    DETAILS.click();

    return new HBDetailsPage();
}
```

---

# 24. Logging

Useful:

```java
Configuration
    .savePageSource = true;
```

---

Screenshots:

```java
Screenshots
    .takeScreenShotAsFile();
```

---

# 25. Handling Tables

Example:

```java
ElementsCollection rows =
    $$("tbody tr");
```

---

First:

```java
rows.first();
```

---

Last:

```java
rows.last();
```

---

Count:

```java
rows.size();
```

---

# 26. Real Example

Current framework:

```java
contentManagementPage
    .goToDetailsOfImportantInformationPage(
        null
    )
    .clickEdit();
```

Breakpoint:

```java
clickEdit()
```

Verify:

```java
this
```

during DAP debugging.

---

# 27. Anti-Patterns

Do NOT:

```java
Thread.sleep()
```

---

Do NOT:

```java
By.xpath(
 "/html/body/div/..."
)
```

---

Do NOT:

```java
click()
without validation
```

---

Do NOT:

```java
Duplicate locators
```

---

# 28. Practical Exercises

## Exercise 1

Replace:

```java
Thread.sleep(5000);
```

with:

```java
element.shouldBe(
    Condition.visible
);
```

---

## Exercise 2

Convert:

```java
driver.findElement(...)
```

to:

```java
SelenideElement
```

---

## Exercise 3

Create:

```java
ElementsCollection
```

for all rows.

---

# 29. Practical Challenge

Given:

```java
MainRecipientPage
```

Create:

```java
ElementsCollection rows;
```

---

Find:

```java
mainRecipientName
```

without:

```java
for loops
```

---

Use:

```java
findBy(
    Condition.text(...)
)
```

---

# 30. Troubleshooting

## Element Not Found

Verify:

```java
Condition.visible
```

used.

---

## Element Hidden

Use:

```java
scrollIntoView(true)
```

---

## Collection Empty

Check:

```java
rows.size()
```

during DAP debugging.

---

## Wrong Page

Verify:

```java
waitForPageToLoad();
```

completed.

---

# 31. Daily Practice Routine

Every day:

1. Refactor one locator.
2. Remove one sleep.
3. Replace one XPath.
4. Create one collection.
5. Improve one page object.
6. Add one validation.
7. Review one flaky test.

---

# 32. Mastery Checklist

Before proceeding to Chapter 11:

- [ ] Use SelenideElement
- [ ] Use ElementsCollection
- [ ] Understand Conditions
- [ ] Avoid Thread.sleep()
- [ ] Create stable locators
- [ ] Build Page Objects
- [ ] Build Fluent APIs
- [ ] Use collections correctly
- [ ] Handle tables
- [ ] Debug Selenide Tests
- [ ] Remove flaky waits
- [ ] Apply best practices

---

# Chapter Summary

After completing this chapter you should be able to:

- Build maintainable Page Objects
- Reduce flaky tests
- Handle complex tables
- Create reusable framework components
- Write cleaner Selenide code
- Debug UI failures efficiently

The next chapter:

```markdown
# Chapter 11 - Test Automation Patterns
```

will cover:

- Builder Pattern
- Factory Pattern
- Strategy Pattern
- Fluent APIs
- Test Data Builders
- Page Object Design Patterns
- Framework Architecture
- Enterprise Automation Practices

# Chapter 11 - Test Automation Patterns

#table-of-contents

---

# 1. Introduction

As automation frameworks grow, code quality becomes more important than test quantity.

A framework with:

```text
500 tests
```

and poor design is harder to maintain than:

```text
2000 tests
```

using good patterns.

This chapter focuses on the patterns most commonly used in:

- TestNG
- Selenide
- Robot Framework integrations
- API Testing
- Enterprise Automation Frameworks

The goal is:

```text
Maintainability
Reusability
Readability
Scalability
```

---

# 2. Why Patterns Matter

Without patterns:

```java
@Test
public void testLogin() {

    $("#username")
        .setValue("admin");

    $("#password")
        .setValue("admin");

    $("#login")
        .click();

}
```

Problems:

```text
Duplicated code
Hard maintenance
Fragile tests
```

---

Using patterns:

```java
loginPage
    .login(
        "admin",
        "admin"
    );
```

---

Benefits:

```text
Cleaner code
Reusable code
Lower maintenance cost
```

---

# 3. Page Object Pattern

Most important UI automation pattern.

Purpose:

```text
Separate tests from UI details
```

---

Bad:

```java
@Test
public void testLogin() {

    $("#username")
        .setValue("admin");

    $("#password")
        .setValue("admin");

    $("#btnLogin")
        .click();
}
```

---

Good:

```java
@Test
public void testLogin() {

    loginPage.login(
        "admin",
        "admin"
    );
}
```

---

# 4. Page Object Structure

Recommended:

```text
Page
├── Locators
├── Actions
├── Validations
└── Navigation
```

---

Example:

```java
public class LoginPage {

    private final SelenideElement
        USERNAME;

    private final SelenideElement
        PASSWORD;

    public HomePage login(
            String user,
            String pass) {

        USERNAME.setValue(user);

        PASSWORD.setValue(pass);

        return new HomePage();
    }
}
```

---

# 5. Fluent API Pattern

One of the most common enterprise automation patterns.

---

Goal:

```text
Readable test flows
```

---

Example:

```java
contentManagementPage
    .clickEdit()
    .save()
    .validate();
```

---

Instead of:

```java
contentManagementPage.clickEdit();

contentManagementPage.save();

contentManagementPage.validate();
```

---

# 6. Building Fluent APIs

Example:

```java
public class LoginPage {

    public LoginPage
    enterUsername(
            String username) {

        USERNAME.setValue(
            username
        );

        return this;
    }

}
```

---

Usage:

```java
loginPage
    .enterUsername("admin")
    .enterPassword("admin")
    .clickLogin();
```

---

# 7. Self Referencing Generics

Useful for inheritance.

---

Example:

```java
public abstract class
CMDetailsPage<
    T extends CMDetailsPage<T>
>
```

---

Implementation:

```java
@SuppressWarnings(
    "unchecked"
)
@Override
public T getInstance() {

    return (T) this;
}
```

---

Benefit:

```text
Strong typing
Fluent inheritance
```

---

# 8. Builder Pattern

Used for creating complex objects.

---

Without Builder:

```java
User user =
    new User(
        username,
        password,
        country,
        role
    );
```

---

With Builder:

```java
User user =
    UserBuilder
        .aUser()
        .withUsername(
            "admin"
        )
        .withPassword(
            "secret"
        )
        .withCountry(
            "PT"
        )
        .build();
```

---

# 9. Test Data Builder Pattern

Very useful for test automation.

---

Example:

```java
DocumentData data =
    DocumentDataBuilder
        .aDocument()
        .withCountry(
            "Portugal"
        )
        .withDocumentType(
            "Passport"
        )
        .build();
```

---

Advantages:

```text
Readable
Reusable
Flexible
```

---

# 10. Factory Pattern

Used when objects vary.

---

Example:

```java
UserFactory
    .createPublisher();
```

---

Implementation:

```java
public static User
createPublisher() {

    return new User(
        "publisher@test.com",
        "password"
    );
}
```

---

# 11. Strategy Pattern

Useful when behavior changes.

---

Example:

Different login methods:

```text
Username/Password
SAML
OAuth
```

---

Interface:

```java
public interface
AuthenticationStrategy {

    void authenticate();
}
```

---

Implementation:

```java
public class
SamlAuthenticationStrategy
```

---

Implementation:

```java
public class
PasswordAuthenticationStrategy
```

---

Usage:

```java
strategy.authenticate();
```

---

# 12. Repository Pattern

Useful for test data.

---

Example:

```java
UserRepository
```

contains:

```java
Publisher
Creator
Validator
Admin
```

---

Example:

```java
User user =
    UserRepository
        .publisher();
```

---

# 13. BaseTest Pattern

Most frameworks use:

```java
BaseTest
```

---

Example:

```java
public abstract class
BaseTest {

    @BeforeMethod
    public void setup() {

    }
}
```

---

Usage:

```java
public class
ContentManagementTest
extends BaseTest {
}
```

---

# 14. Service Pattern

Common in API automation.

---

Example:

```java
AuthenticationService
```

---

Instead of:

```java
RestAssured
    .given()
    ...
```

inside tests.

---

Tests call:

```java
authenticationService
    .login();
```

---

# 15. AuthenticationCalls Pattern

Based on your SAML implementation.

---

Example:

```java
authenticationCalls
    .authenticate()
```

---

Responsibilities:

```text
Headers
Cookies
CSRF
SAML
PKCE
```

---

Tests remain simple.

---

# 16. Page Component Pattern

Useful for reusable sections.

---

Example:

```text
Header
Sidebar
Footer
```

---

Structure:

```java
SidebarComponent
```

---

Example:

```java
sidebar
    .openDocuments();
```

---

# 17. Avoid God Objects

Bad:

```java
ContentManagementPage
```

with:

```text
300 methods
```

---

Prefer:

```text
ContentManagementPage
DetailsPage
EditPage
TableComponent
```

---

Smaller objects.

---

# 18. Configuration Pattern

Centralize:

```text
URLs
Credentials
Environments
Timeouts
```

---

Example:

```java
Config.getBaseUrl();
```

---

Instead of:

```java
"https://test.server"
```

hardcoded.

---

# 19. Enum Pattern

Very useful.

---

Bad:

```java
goToContent(
    "IMPORTANT_INFORMATION"
);
```

---

Better:

```java
goToContent(
    EContentManagement
        .IMPORTANTINFORMATION
);
```

---

Benefits:

```text
Compile safety
Autocomplete
Refactoring support
```

---

# 20. State Pattern

Useful for workflow testing.

---

Example:

```text
Draft
Published
Archived
Deleted
```

---

Represent:

```java
DocumentState
```

instead of strings.

---

# 21. Common Pattern Combination

Typical enterprise framework:

```text
BaseTest
 ├── Page Objects
 ├── Components
 ├── Builders
 ├── Factories
 ├── Repositories
 └── Services
```

---

# 22. Framework Architecture Example

```text
tests
│
├── ContentManagementTest
│
pages
│
├── ContentManagementPage
├── HBDetailsPage
└── LoginPage
│
services
│
├── AuthenticationService
│
builders
│
├── UserBuilder
│
factories
│
├── UserFactory
```

---

# 23. Practical Exercise

Create:

```java
PublisherUserBuilder
```

Capable of:

```java
PublisherUserBuilder
    .aPublisher()
    .withCountry(
        "PT"
    )
    .build();
```

---

# 24. Practical Exercise

Convert:

```java
String role =
    "PUBLISHER";
```

into:

```java
ERole.PUBLISHER
```

---

# 25. Practical Challenge

Refactor:

```java
public void login() {

    USERNAME
        .setValue(
            "admin"
        );

    PASSWORD
        .setValue(
            "admin"
        );

    BTN_LOGIN.click();
}
```

into:

```java
loginPage.login(
    user,
    password
);
```

using:

```text
Page Object
Service
Builder
```

---

# 26. Anti Patterns

Avoid:

```text
God Objects
Copy/Paste
Thread.sleep()
Hardcoded Users
Hardcoded URLs
Duplicated Locators
```

---

Avoid:

```java
new User(...)
```

everywhere.

Use:

```java
Builders
```

instead.

---

# 27. Real Framework Example

Current:

```java
contentManagementPage
    .goToDetailsOfImportantInformationPage(
        null
    )
    .clickEdit()
```

Patterns used:

```text
Page Object
Fluent API
```

---

Potential improvements:

```text
Builder
Factory
Repository
```

---

# 28. Daily Practice Routine

Every day:

1. Refactor one duplicated block.
2. Create one builder.
3. Create one enum.
4. Extract one service.
5. Simplify one page object.
6. Remove one hardcoded value.

---

# 29. Mastery Checklist

Before proceeding to Chapter 12:

- [ ] Understand Page Objects
- [ ] Understand Fluent APIs
- [ ] Use Builders
- [ ] Use Factories
- [ ] Use Services
- [ ] Use Repositories
- [ ] Use Enums
- [ ] Use Components
- [ ] Centralize Configurations
- [ ] Avoid God Objects
- [ ] Build Scalable Frameworks

---

# 30. Chapter Summary

After this chapter you should be able to:

- Design maintainable automation frameworks
- Apply enterprise design patterns
- Create reusable test data
- Build scalable Page Objects
- Reduce technical debt
- Improve test readability and maintainability

The next chapter:

```markdown
# Chapter 12 - Java Generics
```

will cover:

- Generic Types
- Wildcards
- Bounds
- Self Referencing Generics
- Fluent APIs with Generics
- Test Framework Examples
- CMDetailsPage Patterns
- Common Compilation Errors
- Generic Design Best Practices

# Chapter 12 - Java Generics

#table-of-contents

---

# 1. Introduction

Generics are one of the most important features in Java.

They allow:

- Type Safety
- Code Reuse
- Cleaner APIs
- Compile-Time Validation
- Fluent APIs
- Framework Design

Virtually every modern Java framework uses generics:

```text
Spring
JUnit
TestNG
Selenide
Hibernate
Jackson
```

Your automation framework already uses generics:

```java
CMDetailsPage<T extends CMDetailsPage<T>>
```

and

```java
IGenericMethods<T>
```

This chapter explains how generics work and how to use them correctly in automation frameworks.

---

# 2. Why Generics Exist

Without generics:

```java
List users =
    new ArrayList();
```

Java only knows:

```text
Object
```

---

Example:

```java
users.add("John");

users.add(123);

users.add(true);
```

Everything compiles.

---

Problems discovered only at runtime.

---

With Generics:

```java
List<String> users =
    new ArrayList<>();
```

Now:

```java
users.add("John");
```

works.

---

But:

```java
users.add(123);
```

fails at compile time.

---

# 3. Basic Generic Syntax

Generic Type:

```java
List<String>
```

---

Custom Generic:

```java
public class Box<T> {

    private T value;

}
```

---

Usage:

```java
Box<String> box =
    new Box<>();
```

---

# 4. Multiple Generic Types

Example:

```java
Map<String, Integer>
```

Has:

```java
K = String
V = Integer
```

---

Custom Example:

```java
public class Pair<K, V> {

    private K key;

    private V value;

}
```

---

Usage:

```java
Pair<String, Integer> pair =
    new Pair<>();
```

---

# 5. Generic Methods

Example:

```java
public <T> T identity(
        T value) {

    return value;
}
```

---

Usage:

```java
String result =
    identity("admin");
```

---

Or:

```java
Integer result =
    identity(123);
```

---

# 6. Generic Collections

Most common:

```java
List<String>
```

```java
Set<String>
```

```java
Map<String, String>
```

```java
Queue<User>
```

---

Framework Example:

```java
List<DocumentData>
```

instead of:

```java
List<Object>
```

---

# 7. Why Raw Types Are Dangerous

Avoid:

```java
List list =
    new ArrayList();
```

---

Prefer:

```java
List<String> list =
    new ArrayList<>();
```

---

Raw types remove:

```text
Compile Safety
Refactoring Safety
Autocomplete
```

---

# 8. Upper Bounds

Example:

```java
<T extends Number>
```

Meaning:

```text
T must be a Number
```

---

Valid:

```java
Integer
Double
Long
Float
```

---

Invalid:

```java
String
```

---

Example:

```java
public <T extends Number>
void calculate(T value) {

}
```

---

# 9. Multiple Bounds

Example:

```java
<T extends Number & Comparable<T>>
```

Must satisfy:

```text
Number
AND
Comparable
```

---

Useful in framework utilities.

---

# 10. Wildcards

Wildcard:

```java
?
```

means:

```text
Unknown Type
```

---

Example:

```java
List<?>
```

---

Accepts:

```java
List<String>
List<Integer>
List<User>
```

---

# 11. Upper Wildcards

```java
List<? extends User>
```

Accepts:

```java
AdminUser
PublisherUser
CreatorUser
```

---

Useful for reading collections.

---

# 12. Lower Wildcards

```java
List<? super User>
```

Means:

```text
User or Parent Types
```

---

Used mostly for insertion.

---

# 13. Generic Interfaces

Example:

```java
public interface Repository<T> {

    T find();

}
```

---

Implementation:

```java
public class UserRepository
implements Repository<User> {

}
```

---

# 14. Generic Framework Pattern

Your framework:

```java
public interface
IGenericMethods<T>
```

Contains:

```java
T getInstance();
```

---

Benefit:

```text
Method chaining
Correct return types
```

---

# 15. Problem Without Generics

Example:

```java
public Object clickEdit() {

    click(BTN_EDIT);

    return this;
}
```

---

Usage:

```java
page
    .clickEdit()
```

returns:

```java
Object
```

---

Cannot chain methods safely.

---

# 16. Better Solution

Generic return:

```java
public T clickEdit() {

    click(BTN_EDIT);

    return getInstance();
}
```

---

Now:

```java
page
    .clickEdit()
    .validate();
```

works.

---

# 17. Self Referencing Generics

The most important pattern in your framework.

---

Example:

```java
public abstract class
CMDetailsPage<
    T extends CMDetailsPage<T>
>
```

---

Purpose:

```text
Return child type
instead of parent type
```

---

# 18. Why Self Referencing Is Needed

Without:

```java
class CMDetailsPage {

}
```

Methods return:

```java
CMDetailsPage
```

---

Example:

```java
clickEdit()
```

returns:

```java
CMDetailsPage
```

---

You lose access to child methods.

---

# 19. CMDetailsPage Pattern

Your real framework:

```java
public abstract class
CMDetailsPage<
    T extends CMDetailsPage<T>
>
implements IGenericMethods<T> {
}
```

---

And:

```java
@Override
@SuppressWarnings("unchecked")
public T getInstance() {

    return (T) this;
}
```

---

# 20. Child Implementation

Example:

```java
public class
HBDetailsPage
extends
CMDetailsPage<
    HBDetailsPage
> {

}
```

---

Now:

```java
HBDetailsPage
```

becomes:

```java
T
```

inside parent methods.

---

# 21. Fluent API Example

Parent:

```java
public T clickEdit() {

    click(BTN_EDIT);

    return getInstance();
}
```

---

Usage:

```java
hbDetailsPage
    .clickEdit()
    .validate()
    .save();
```

---

Compile-time safe.

---

# 22. Another Framework Example

Example:

```java
public abstract class
BasePage<T extends BasePage<T>>
```

---

Child:

```java
LoginPage
extends BasePage<LoginPage>
```

---

Child:

```java
HomePage
extends BasePage<HomePage>
```

---

Very common enterprise pattern.

---

# 23. Common Compilation Error

Example:

```text
return type incompatible with T
```

---

Cause:

```java
public Object getInstance()
```

instead of:

```java
public T getInstance()
```

---

# 24. Error From Your Framework

Problem:

```java
CMDetailsPage<CMDetailsPage>
```

---

Compiler:

```text
Type argument is not
within bounds of T
```

---

Reason:

```java
CMDetailsPage
```

does not satisfy:

```java
T extends CMDetailsPage<T>
```

---

Solution:

```java
public T getInstance() {
    return (T) this;
}
```

---

# 25. Error Example

Wrong:

```java
@Override
public Object getInstance() {

    return this;
}
```

---

Correct:

```java
@Override
public T getInstance() {

    return (T) this;
}
```

---

# 26. Generic Builder Pattern

Example:

```java
public abstract class
Builder<T> {

    public abstract T build();

}
```

---

Implementation:

```java
UserBuilder
extends Builder<User>
```

---

# 27. Generic Repository Pattern

Example:

```java
public interface
Repository<T> {

    T findById(
        String id
    );

}
```

---

Implementation:

```java
UserRepository
implements Repository<User>
```

---

# 28. Practical Exercise

Create:

```java
BasePage<T>
```

with:

```java
public T clickSave()
```

returning:

```java
getInstance()
```

---

# 29. Practical Exercise

Implement:

```java
UserRepository
implements Repository<User>
```

---

Add:

```java
findById()
```

---

# 30. Practical Exercise

Create:

```java
DocumentBuilder
```

using:

```java
Builder<Document>
```

---

Build:

```java
Document
```

instance.

---

# 31. Practical Challenge

Refactor:

```java
public Object clickEdit()
```

into:

```java
public T clickEdit()
```

---

Then enable:

```java
page
    .clickEdit()
    .save()
    .validate();
```

---

# 32. Common Mistakes

Avoid:

```java
List list
```

---

Avoid:

```java
Map map
```

---

Avoid:

```java
Object everywhere
```

---

Avoid:

```java
@SuppressWarnings
```

unless necessary.

---

# 33. Real Framework Review

Current Framework Uses:

```java
CMDetailsPage<T>
```

✅ Good

---

```java
IGenericMethods<T>
```

✅ Good

---

```java
T getInstance()
```

✅ Good

---

Allows:

```java
HBDetailsPage
LegalInformationDetailsPage
```

to retain their type.

---

# 34. Daily Practice Routine

Every day:

1. Create one generic collection.
2. Build one generic interface.
3. Review one framework class.
4. Replace one Object with T.
5. Create one builder.
6. Create one repository.

---

# 35. Mastery Checklist

Before proceeding to Chapter 13:

- [ ] Understand Generic Types
- [ ] Understand Generic Methods
- [ ] Use Generic Collections
- [ ] Understand Bounds
- [ ] Understand Wildcards
- [ ] Create Generic Interfaces
- [ ] Create Generic Builders
- [ ] Create Generic Repositories
- [ ] Understand Self Referencing Generics
- [ ] Understand CMDetailsPage<T>
- [ ] Debug Generic Compilation Errors
- [ ] Build Fluent APIs With Generics

---

# 36. Chapter Summary

After completing this chapter you should be able to:

- Understand Java Generics deeply
- Read enterprise framework code confidently
- Build fluent APIs safely
- Design scalable automation frameworks
- Debug generic compilation issues
- Extend your framework correctly

The next chapter:

```markdown
# Chapter 13 - Robot Framework Structure
```

will cover:

- Framework Layout
- Resources
- Libraries
- Variables
- Keywords
- Tags
- Parallel Execution
- API Testing
- GUI Testing
- Integration with Python and Java

# Chapter 13 - Robot Framework Structure

#table-of-contents

---

# 1. Introduction

Robot Framework is an open-source automation framework designed for:

- GUI Testing
- API Testing
- Integration Testing
- Acceptance Testing
- End-to-End Testing

Key characteristics:

```text
Keyword Driven
Human Readable
Easy To Learn
Extensible
```

For your automation architecture it is especially useful because:

```text
Junior Testers
Business Users
Automation Engineers
```

can work together.

---

# 2. Where Robot Fits In Your Ecosystem

Current ecosystem:

```text
Java + TestNG + Selenide
│
├── UI Testing
├── API Testing
├── Framework Logic
│
Robot Framework
│
├── Business Flows
├── Reusable Keywords
├── Test Suites
│
Locust
│
├── Performance Tests
│
OWASP ZAP
│
├── Security Tests
```

Goal:

```text
One ecosystem
Multiple test types
```

---

# 3. Recommended Project Structure

Based on your current discussions:

```text
Python Testing
│
├── robotFrameworkTesting
│
│   ├── resources
│   │
│   ├── libraries
│   │
│   ├── testdata
│   │
│   ├── tests
│   │
│   ├── reports
│   │
│   └── results
│
├── locustPerformanceTesting
│
└── zapSecurityTesting
```

---

# 4. Robot Framework Structure

Recommended:

```text
robotframework
│
├── tests
│
├── resources
│
├── libraries
│
├── variables
│
├── data
│
└── reports
```

---

# 5. tests Folder

Contains:

```text
Actual test cases
```

Example:

```text
tests
│
├── login.robot
├── events.robot
├── publication.robot
└── content_management.robot
```

---

Example:

```robot
*** Test Cases ***

User Can Login

    Open Browser

    Login As Publisher

    Verify Dashboard
```

---

# 6. resources Folder

Contains:

```text
Reusable Keywords
```

---

Example:

```text
resources
│
├── common.robot
├── login.robot
├── navigation.robot
└── content_management.robot
```

---

Example:

```robot
*** Keywords ***

Login As Publisher

    Input Text

    Click Button
```

---

# 7. variables Folder

Contains:

```text
Constants
URLs
Credentials
```

---

Example:

```robot
*** Variables ***

${BASE_URL}

${USERNAME}

${PASSWORD}
```

---

File:

```text
variables/environment.robot
```

---

# 8. libraries Folder

Contains:

```text
Custom Python Libraries
```

---

Example:

```text
libraries
│
├── AuthenticationLibrary.py
├── ContentManagementLibrary.py
└── CommonLibrary.py
```

---

Usage:

```robot
Library
    AuthenticationLibrary.py
```

---

# 9. Test Case Structure

Recommended:

```robot
*** Settings ***

*** Variables ***

*** Test Cases ***

*** Keywords ***
```

---

Template:

```robot
*** Test Cases ***

Verify Login

    Open Browser

    Login

    Verify User Logged
```

---

# 10. Keyword Design

Bad:

```robot
Do Everything
```

---

Good:

```robot
Open Browser

Login

Navigate To Content Management

Create Important Information

Verify Success Message
```

---

# 11. Tags

Robot equivalent of:

```java
@Test(groups={})
```

---

Example:

```robot
[Tags]
smoke
publisher
content_management
```

---

Execution:

```bash
robot --include smoke
```

---

# 12. Variables Files

Example:

```robot
${BROWSER}    chrome

${URL}        https://test.server
```

---

Or:

```python
URL = "https://test.server"
```

---

Usage:

```robot
Variables
    env.py
```

---

# 13. Reusing Existing Payloads

Based on your project:

Current payloads:

```text
locustPerformanceTesting
│
└── payloads
```

---

Reuse:

```text
robotFrameworkTesting
```

through:

```python
Path
Libraries
Shared modules
```

---

Goal:

```text
One Payload Source

Multiple Test Types
```

---

# 14. Custom Python Libraries

Example:

```python
class AuthenticationLibrary:

    def login(self):

        pass
```

---

Robot:

```robot
Login
```

becomes available.

---

# 15. API Testing

Import:

```robot
Library
    RequestsLibrary
```

---

Example:

```robot
Create Session
```

```robot
GET On Session
```

---

Example:

```robot
*** Test Cases ***

Get Documents

    Create Session

    GET On Session

    Should Be Equal
```

---

# 16. Browser Automation

Current recommendation:

```text
Browser Library
```

instead of:

```text
SeleniumLibrary
```

for new projects.

---

Installation:

```bash
pip install robotframework-browser
```

---

Initialize:

```bash
rfbrowser init
```

---

# 17. Browser Library Example

```robot
*** Test Cases ***

Login

    New Browser

    New Page

    Go To
        ${URL}

    Fill Text

    Click

    Close Browser
```

---

# 18. Integration With Java Systems

Robot can interact with:

```text
REST APIs

Databases

Java Applications

Message Queues
```

through:

```python
Libraries
```

---

# 19. Integration With Existing Java Framework

Current architecture:

```text
Java
│
├── Selenide
├── TestNG
│
Robot
│
├── Browser
├── Requests
```

---

Recommended:

```text
Robot
    ↓

Python Libraries

    ↓

Shared Services

    ↓

Common Test Data
```

---

# 20. User-Based Test Structure

Your discussed architecture:

```text
users
│
├── creator
├── publisher
├── validator
```

---

Recommended:

```text
tests
│
├── creator
│
├── publisher
│
└── validator
```

---

# 21. Eurosur Structure Example

Example:

```text
tests
│
├── eurosur10
│
│   ├── events
│   ├── operations
│   └── analysis
│
└── eurosur15
    ├── events
    ├── operations
    └── analysis
```

---

# 22. Running Tests

All:

```bash
robot tests
```

---

Single file:

```bash
robot tests/login.robot
```

---

Single tag:

```bash
robot --include smoke
```

---

Exclude:

```bash
robot --exclude regression
```

---

# 23. Parallel Execution

Library:

```text
Pabot
```

Install:

```bash
pip install robotframework-pabot
```

---

Run:

```bash
pabot tests
```

---

Example:

```bash
pabot --processes 4 tests
```

---

# 24. Reports

Generated automatically.

---

Files:

```text
report.html
```

```text
log.html
```

```text
output.xml
```

---

Open:

```bash
xdg-open report.html
```

---

# 25. Debugging Robot Tests

Increase logs:

```bash
robot --loglevel DEBUG
```

---

Add:

```robot
Log
```

---

Example:

```robot
Log
    Current User
```

---

# 26. Practical Exercise

Create:

```robot
Login As Publisher
```

keyword.

---

Expected:

```robot
*** Keywords ***

Login As Publisher

    Input Text

    Input Password

    Click
```

---

# 27. Practical Exercise

Execute:

```robot
Smoke Suite
```

only.

Solution:

```bash
robot --include smoke
```

---

# 28. Practical Exercise

Create:

```robot
Content Management
```

suite.

---

Contains:

```text
Add Entry
Edit Entry
Delete Entry
```

---

# 29. Practical Challenge

Build:

```text
creator
publisher
validator
```

folder structure.

---

Add:

```text
smoke
regression
```

tags.

---

Execute only:

```text
publisher smoke
```

tests.

---

Expected:

```bash
robot \
--include publisher \
--include smoke
```

---

# 30. Common Problems

## Library Not Found

Verify:

```bash
pip list
```

---

## Browser Fails

Initialize:

```bash
rfbrowser init
```

---

## Variable Missing

Verify:

```robot
${VARIABLE}
```

exists.

---

## Tag Not Executed

Verify:

```robot
[Tags]
```

configuration.

---

# 31. Daily Practice Routine

Every day:

1. Create one keyword.
2. Create one resource.
3. Create one test case.
4. Execute one tag.
5. Review reports.
6. Refactor one keyword.
7. Reduce duplication.

---

# 32. Mastery Checklist

Before proceeding to Chapter 14:

- [ ] Understand Robot Structure
- [ ] Build Resources
- [ ] Build Keywords
- [ ] Use Variables
- [ ] Create Libraries
- [ ] Execute Tags
- [ ] Use Browser Library
- [ ] Use RequestsLibrary
- [ ] Run Parallel Tests
- [ ] Read Robot Reports
- [ ] Integrate Python Libraries
- [ ] Organize User-Based Suites

---

# 33. Chapter Summary

After completing this chapter you should be able to:

- Design Robot Framework projects
- Build reusable keywords
- Integrate Python libraries
- Organize large test suites
- Execute tests efficiently
- Generate useful reports
- Scale Robot in enterprise environments

The next chapter:

```markdown
# Chapter 14 - Locust Performance Testing
```

will cover:

- Locust Architecture
- User Classes
- Tasks
- Wait Times
- Reports
- CSV Outputs
- Load Profiles
- CI/CD Integration
- Performance Best Practices

# Chapter 14 - Locust Performance Testing

#table-of-contents

---

# 1. Introduction

Locust is an open-source performance testing framework written in Python.

Unlike traditional tools such as:

```text
JMeter
LoadRunner
Gatling
```

Locust focuses on:

```text
Code
Flexibility
Automation
CI/CD Integration
Scalability
```

For your ecosystem, Locust is ideal because:

```text
Python
Robot Framework
REST APIs
CI Pipelines
```

can all share resources and test data.

---

# 2. Performance Testing Concepts

Before using Locust, understand the most important metrics.

---

## Response Time

Time taken for one request.

Example:

```text
GET /documents

250 ms
```

---

## Throughput

Number of requests processed.

Example:

```text
500 requests/s
```

---

## Concurrent Users

Number of active users.

Example:

```text
100 users
```

---

## Error Rate

Failed requests.

Example:

```text
2%
```

---

## Percentiles

Most important metric.

Example:

```text
P50
P90
P95
P99
```

Meaning:

```text
95% of users received a response
within the reported value
```

---

# 3. Why Percentiles Matter

Average:

```text
300 ms
```

looks good.

---

P95:

```text
2000 ms
```

reveals:

```text
5% of users experience
very slow responses
```

---

Always verify:

```text
P90
P95
P99
```

not just averages.

---

# 4. Installing Locust

Install:

```bash
pip install locust
```

Verify:

```bash
locust --version
```

---

# 5. Project Structure

Recommended:

```text
locustPerformanceTesting
│
├── locustfile.py
│
├── users
│
├── tasks
│
├── payloads
│
├── reports
│
└── utils
```

---

Based on your setup:

```text
Python Testing
│
├── locustPerformanceTesting
│
└── payloads
```

Payloads should be reusable by:

```text
Locust
Robot Framework
Security Testing
```

---

# 6. First Locust Test

Example:

```python
from locust import HttpUser, task

class User(HttpUser):

    @task
    def homepage(self):
        self.client.get("/")
```

---

Run:

```bash
locust
```

Open:

```text
http://localhost:8089
```

---

# 7. Understanding HttpUser

Each instance represents:

```text
One Virtual User
```

---

Example:

```python
class PublisherUser(HttpUser):
```

---

Possible users:

```text
PublisherUser
CreatorUser
ValidatorUser
AdminUser
```

---

Matches your application roles.

---

# 8. Tasks

Users perform tasks.

Example:

```python
@task
def login(self):
```

---

Example:

```python
@task
def get_documents(self):
```

---

Execution:

```text
User
 ├── Login
 ├── Search
 └── Logout
```

---

# 9. Multiple Tasks

Example:

```python
from locust import HttpUser, task
```

```python
class PublisherUser(HttpUser):

    @task
    def search_document(self):
        pass

    @task
    def open_document(self):
        pass
```

Locust executes randomly.

---

# 10. Task Weighting

Control frequency.

Example:

```python
@task(5)
def search_document(self):
    pass
```

---

```python
@task(1)
def delete_document(self):
    pass
```

---

Meaning:

```text
Search
≈ 5 times more often
```

than:

```text
Delete
```

---

# 11. Wait Times

Avoid unrealistic traffic.

---

Example:

```python
from locust import between
```

```python
wait_time =
    between(1, 5)
```

---

Users wait:

```text
1 to 5 seconds
```

between actions.

---

# 12. Realistic User Behaviour

Bad:

```python
wait_time =
    between(0, 0)
```

---

Produces:

```text
Artificial Load
```

---

Better:

```python
between(2, 10)
```

for business users.

---

# 13. Requests

Example:

```python
response =
    self.client.get(
        "/documents"
    )
```

---

POST:

```python
self.client.post(
    "/documents",
    json=payload
)
```

---

PUT:

```python
self.client.put(...)
```

---

DELETE:

```python
self.client.delete(...)
```

---

# 14. Reusing Payloads

Current structure:

```text
payloads
```

---

Load:

```python
import json
```

```python
with open(
        "payloads/document.json"
) as file:

    payload =
        json.load(file)
```

---

Use same payloads in:

```text
Locust
Robot Framework
API Testing
```

---

# 15. Authentication

Simple:

```python
self.client.post(
    "/login"
)
```

---

Store:

```python
token
```

---

Reuse:

```python
headers = {
    "Authorization":
    f"Bearer {token}"
}
```

---

# 16. Test Lifecycle

Setup:

```python
def on_start(self):
```

---

Cleanup:

```python
def on_stop(self):
```

---

Example:

```python
def on_start(self):

    self.login()
```

---

# 17. Test Data Strategy

Avoid:

```text
One Shared User
```

---

Prefer:

```text
User Pool
```

Example:

```text
publisher1
publisher2
publisher3
```

---

# 18. Running Locust

Start:

```bash
locust
```

---

Headless:

```bash
locust \
--headless
```

---

Example:

```bash
locust \
-u 100 \
-r 10
```

Meaning:

```text
100 users
10 users/sec
```

---

# 19. Ramp-Up

Example:

```bash
locust \
-u 500 \
-r 25
```

---

Meaning:

```text
25 users
added every second
```

until:

```text
500 users
```

are reached.

---

# 20. Run Time

Example:

```bash
locust \
-u 100 \
-r 10 \
--run-time 15m
```

---

Test duration:

```text
15 minutes
```

---

# 21. Reports

Locust UI exposes:

```text
Requests
Failures
Percentiles
Charts
```

---

Most important:

```text
P95
Error Rate
Throughput
```

---

# 22. CSV Output

Generate:

```bash
locust \
--headless \
-u 100 \
-r 10 \
--csv reports/run
```

---

Creates:

```text
run_stats.csv
run_failures.csv
run_history.csv
```

---

# 23. Reading CSV Files

Useful columns:

```text
Request Name
Response Time
Failures
Users
```

---

Analyze:

```python
pandas
```

or:

```text
Excel
```

---

# 24. Throughput Analysis

Example:

```text
200 req/s
```

Good.

---

If:

```text
P95 = 50ms
```

excellent.

---

If:

```text
P95 = 5s
```

system bottleneck.

---

# 25. Performance Thresholds

Example SLA:

```text
P95 < 2s

Error Rate < 1%

Availability > 99%
```

---

Define these before testing.

---

# 26. CI/CD Integration

Run:

```bash
locust \
--headless
```

inside:

```text
Azure DevOps
GitLab
GitHub Actions
Jenkins
```

---

Fail build if:

```text
Error Rate > 1%
```

---

# 27. Example CI Pipeline

```bash
locust \
-u 100 \
-r 10 \
--run-time 10m \
--headless
```

Generate:

```text
CSV Reports
```

Upload as artifacts.

---

# 28. Practical Exercise

Create:

```python
PublisherUser
```

with:

```python
login()
open_document()
logout()
```

tasks.

---

# 29. Practical Exercise

Load:

```text
payloads/document.json
```

and send:

```python
POST
```

request.

---

# 30. Practical Challenge

Build a simulation:

```text
50 Publishers
25 Creators
25 Validators
```

---

Each performs:

```text
Login
Search
Open Document
Logout
```

---

Measure:

```text
P95
P99
Error Rate
Throughput
```

---

# 31. Common Problems

## Too Many Errors

Check:

```text
Authentication
Permissions
Rate Limits
```

---

## Throughput Too Low

Check:

```text
Backend
Database
Network
```

---

## P95 High

Investigate:

```text
Slow Queries
Large Payloads
Blocking APIs
```

---

## User Collisions

Avoid:

```text
Same Test User
```

for all virtual users.

---

# 32. Daily Practice Routine

Every day:

1. Run one small load test.
2. Analyze one CSV report.
3. Review P95.
4. Review Error Rate.
5. Add one reusable payload.
6. Refactor one task.

---

# 33. Mastery Checklist

Before proceeding to Security Testing:

- [ ] Understand HttpUser
- [ ] Create Tasks
- [ ] Configure Wait Times
- [ ] Reuse Payloads
- [ ] Authenticate Users
- [ ] Execute Headless Tests
- [ ] Generate Reports
- [ ] Generate CSV Files
- [ ] Interpret P95
- [ ] Interpret P99
- [ ] Measure Throughput
- [ ] Integrate with CI/CD

---

# 34. Chapter Summary

After completing this chapter you should be able to:

- Build realistic performance tests
- Simulate real user behaviour
- Measure application performance
- Analyze latency and throughput
- Generate performance reports
- Integrate Locust into CI/CD pipelines

The next chapter:

```markdown
# Chapter 15 - OWASP ZAP
```

will cover:

- Security Testing Fundamentals
- Passive Scan
- Active Scan
- Authentication
- Session Handling
- API Security Testing
- Automation
- Reporting
- CI/CD Integration

# Chapter 15 - OWASP ZAP

#table-of-contents

---

# 1. Introduction

OWASP ZAP (Zed Attack Proxy) is one of the most widely used open-source security testing tools.

It is maintained by:

```text
OWASP
(Open Worldwide Application Security Project)
```

ZAP is commonly used for:

- Dynamic Application Security Testing (DAST)
- API Security Testing
- Authentication Testing
- Session Testing
- Vulnerability Detection
- CI/CD Security Gates

For your ecosystem it complements:

```text
TestNG
Selenide
Robot Framework
Locust
Burp Suite
```

---

# 2. Security Testing Types

Before using ZAP, understand the categories.

## SAST

Static Analysis.

Example:

```text
SonarQube
Checkmarx
Fortify
```

Reviews source code.

---

## DAST

Dynamic Analysis.

Example:

```text
OWASP ZAP
Burp Suite
```

Tests running applications.

---

## IAST

Interactive Analysis.

Example:

```text
Contrast Security
Hdiv
```

Combination of runtime and source analysis.

---

# 3. OWASP Top 10

ZAP is primarily used to detect issues relating to:

```text
A01 Broken Access Control
A02 Cryptographic Failures
A03 Injection
A04 Insecure Design
A05 Security Misconfiguration
A06 Vulnerable Components
A07 Authentication Failures
A08 Integrity Failures
A09 Logging Failures
A10 SSRF
```

---

# 4. Installing OWASP ZAP

Download:

```text
https://www.zaproxy.org/download/
```

Verify installation:

```bash
zap.sh
```

or:

```bash
zaproxy
```

---

# 5. ZAP Architecture

Typical flow:

```text
Browser
   ↓
ZAP Proxy
   ↓
Application
```

---

ZAP intercepts:

```text
Requests
Responses
Headers
Cookies
Tokens
```

---

# 6. Configure Browser Proxy

Example:

```text
Proxy Host:
127.0.0.1

Proxy Port:
8080
```

---

Browser traffic becomes visible in ZAP.

---

# 7. Sites Tree

After browsing:

```text
Sites
 ├── Application
 ├── Endpoints
 ├── Requests
 └── Responses
```

---

Useful for:

```text
Application Reconnaissance
```

---

# 8. Passive Scan

Most commonly used feature.

Passive Scan:

```text
Reads traffic

Does NOT attack
```

---

Detects:

```text
Missing Security Headers
Information Leakage
Cookie Issues
TLS Problems
```

---

Safe to run in production.

---

# 9. Running Passive Scan

Simple workflow:

1. Start ZAP
2. Configure proxy
3. Browse application
4. Review Alerts

---

Typical findings:

```text
X-Frame-Options Missing

CSP Missing

Cookie Missing HttpOnly

Cookie Missing Secure
```

---

# 10. Passive Scan Alerts

Example:

```text
Medium
Cookie Without HttpOnly
```

---

Risk:

```text
Session Theft
```

---

Example:

```text
Medium
Missing Content Security Policy
```

---

Risk:

```text
XSS Exposure
```

---

# 11. Active Scan

Unlike Passive Scan:

```text
Active Scan attacks
the application
```

---

Generates:

```text
Payloads
Manipulated Requests
Security Tests
```

---

Never run against production without approval.

---

# 12. Active Scan Workflow

1. Authenticate
2. Crawl application
3. Select target
4. Start Active Scan

---

ZAP performs:

```text
Injection Tests

XSS Tests

Authentication Tests

Path Manipulation

Header Manipulation
```

---

# 13. Active Scan Findings

Common examples:

```text
Cross-Site Scripting
SQL Injection
Path Traversal
Open Redirect
```

---

Severity:

```text
Low
Medium
High
Critical
```

---

# 14. AJAX Spider

Traditional spider:

```text
Links
```

---

AJAX Spider:

```text
JavaScript Applications
React
Angular
Vue
```

---

Very useful for modern web applications.

---

# 15. Traditional Spider

Example:

```text
Open Application
Run Spider
```

Collects:

```text
URLs
Parameters
Pages
```

---

# 16. Authentication Testing

Critical for enterprise systems.

Verify:

```text
Sessions
Roles
Permissions
```

---

For your projects:

```text
Creator
Publisher
Validator
Admin
```

authentication testing is very important.

---

# 17. Session Handling

Observe:

```text
Cookies
Session IDs
JWT Tokens
```

---

Verify:

```text
Expiration
Logout
Re-authentication
```

---

# 18. API Security Testing

ZAP can test:

```text
REST APIs
OpenAPI
Swagger
GraphQL
```

---

Example endpoint:

```text
/api/documents
```

---

Example:

```text
GET
POST
PUT
DELETE
```

---

# 19. Import OpenAPI Definition

Example:

```text
File

Import OpenAPI
```

---

Result:

```text
All Endpoints Imported
```

---

Useful for automation.

---

# 20. API Scan

After importing:

```text
OpenAPI
```

run:

```text
Active Scan
```

against APIs.

---

Verifies:

```text
Authentication
Authorization
Input Validation
Injection
```

---

# 21. Baseline Scan

One of the most important automation features.

---

Purpose:

```text
Passive Security Assessment
```

---

No attacks.

---

Suitable for:

```text
Production
CI/CD
Nightly Pipelines
```

---

# 22. Running Baseline Scan

Docker:

```bash
docker run \
t/zap-baseline.py \
-t https://example.com
```

---

Result:

```text
HTML Report
XML Report
JSON Report
```

---

# 23. Automation Framework Usage

Recommended workflow:

```text
Deploy
 ↓
Run Baseline
 ↓
Review Findings
 ↓
Promote Build
```

---

# 24. Full Scan

More aggressive.

Example:

```bash
zap-full-scan.py
```

---

Runs:

```text
Spider
Passive Scan
Active Scan
```

---

Not recommended for production.

---

# 25. Automation Scan

Flexible CI/CD approach.

Example:

```bash
zap-api-scan.py
```

Designed for:

```text
APIs
```

---

# 26. Docker Integration

Official images:

```text
owasp/zap2docker-stable
```

---

Example:

```bash
docker run \
owasp/zap2docker-stable
```

---

# 27. CI/CD Integration

Typical pipeline:

```text
Build
 ↓
Deploy
 ↓
ZAP Scan
 ↓
Publish Reports
```

---

Tools:

```text
Azure DevOps
GitHub Actions
GitLab
Jenkins
```

---

# 28. Azure DevOps Example

Pipeline step:

```yaml
- script: |
    zap-baseline.py \
    -t https://test.server
```

---

Artifacts:

```text
report.html
report.xml
```

---

# 29. Reporting

Available formats:

```text
HTML
XML
JSON
Markdown
```

---

HTML report:

```text
Human Reading
```

---

JSON:

```text
Automation
```

---

# 30. Authentication Challenges

Modern systems often use:

```text
OIDC
OAuth2
SAML
PKCE
```

---

Authentication must work before scanning.

---

# 31. Testing Authentication Flows

Verify:

```text
Login
Logout
Session Renewal
Token Refresh
```

---

For your environment:

```text
SAML
RestAssured
PKCE
```

integration becomes important.

---

# 32. Practical Exercise

Run:

```text
Passive Scan
```

against development environment.

---

Identify:

```text
Missing Security Headers
```

---

# 33. Practical Exercise

Import:

```text
Swagger/OpenAPI
```

definition.

---

Run:

```text
API Scan
```

---

Review findings.

---

# 34. Practical Challenge

Scan application using:

```text
Publisher User
```

---

Verify:

```text
Document Creation
Document Editing
Document Viewing
```

---

Check:

```text
Authorization
Session Handling
```

---

# 35. Common Findings

## Missing Security Headers

Example:

```text
X-Frame-Options
```

---

## Cookie Security

Example:

```text
HttpOnly Missing
```

---

## CSP Missing

Example:

```text
Content-Security-Policy
```

---

## Cache Issues

Example:

```text
Sensitive Data Cached
```

---

# 36. Daily Security Routine

Every day:

1. Run one Passive Scan.
2. Review alerts.
3. Review headers.
4. Verify authentication.
5. Verify API responses.
6. Record findings.
7. Track trends.

---

# 37. Mastery Checklist

Before proceeding to Chapter 16:

- [ ] Understand ZAP Architecture
- [ ] Configure Proxy
- [ ] Use Passive Scan
- [ ] Use Active Scan
- [ ] Use AJAX Spider
- [ ] Use Traditional Spider
- [ ] Import OpenAPI
- [ ] Run API Scan
- [ ] Run Baseline Scan
- [ ] Generate Reports
- [ ] Integrate Docker
- [ ] Integrate CI/CD
- [ ] Test Authentication
- [ ] Understand Common Findings

---

# 38. Chapter Summary

After completing this chapter you should be able to:

- Perform web security testing
- Perform API security testing
- Run passive assessments
- Execute active security scans
- Integrate OWASP ZAP into CI/CD
- Interpret security findings
- Validate authentication and session handling

The next chapter:

```markdown
# Chapter 16 - Burp Suite
```

will cover:

- Proxy
- Repeater
- Intruder
- Sequencer
- Decoder
- Comparer
- Extension Ecosystem
- Security Workflows
- Automation Strategies

# Chapter 16 - Burp Suite

#table-of-contents

---

# 1. Introduction

Burp Suite is one of the most widely used web application security testing platforms.

Developed by:

```text
PortSwigger
```

Burp is commonly used for:

- Manual Security Testing
- API Security Testing
- Authentication Analysis
- Session Testing
- Vulnerability Discovery
- Penetration Testing
- Traffic Inspection

For your ecosystem, Burp complements:

```text
Selenide
TestNG
Robot Framework
Locust
OWASP ZAP
RestAssured
SAML Authentication
```

---

# 2. Edition Comparison

## Community Edition

Free.

Includes:

```text
Proxy
Repeater
Decoder
Comparer
```

---

## Professional Edition

Paid.

Adds:

```text
Intruder
Scanner
Extensions
Automation
Collaborator
```

---

Recommended:

```text
Community for learning

Professional for enterprise work
```

---

# 3. Burp Architecture

Traffic flow:

```text
Browser
   ↓
Burp Proxy
   ↓
Application
```

Burp becomes:

```text
Man In The Middle
```

for inspection purposes.

---

# 4. Proxy

Most important feature.

Purpose:

```text
Capture HTTP Traffic
```

---

Burp shows:

```text
Requests
Responses
Headers
Cookies
JWT Tokens
```

---

Typical workflow:

```text
Browser
↓
Proxy
↓
Target
```

---

# 5. Configure Browser

Proxy configuration:

```text
Host:
127.0.0.1

Port:
8080
```

---

Traffic becomes visible.

---

# 6. Intercept

Enable:

```text
Proxy
→ Intercept
→ Intercept On
```

---

Burp pauses every request.

Example:

```http
POST /login
```

---

Modify:

```text
Headers
Payload
Cookies
```

before forwarding.

---

# 7. Request Inspection

Example:

```http
POST /login
```

Request:

```http
username=publisher

password=test123
```

Inspect:

```text
Headers
Cookies
Tokens
Body
```

---

# 8. Response Inspection

Example:

```http
HTTP/1.1 200 OK
```

Review:

```text
Authorization
Session ID
Roles
Permissions
```

---

# 9. HTTP History

Very useful.

Location:

```text
Proxy
→ HTTP History
```

Contains:

```text
Every Request
Every Response
```

---

Useful for:

```text
Reproducing Bugs
Investigating Failures
```

---

# 10. Repeater

One of the most used modules.

---

Purpose:

```text
Replay Requests
```

without using browser automation.

---

Send request:

```text
Right Click
→ Send To Repeater
```

---

# 11. Repeater Workflow

Example:

```http
GET /documents
```

Modify:

```text
Headers
Query Parameters
Tokens
```

---

Send:

```text
Repeat
Repeat
Repeat
```

---

Analyse changes.

---

# 12. API Testing With Repeater

Example:

```http
GET /api/documents
```

---

Modify:

```http
Authorization:
Bearer invalid-token
```

---

Expected:

```http
401 Unauthorized
```

---

Verify authorization checks.

---

# 13. Repeater Usage For SAML

Very useful.

Inspect:

```text
SAML Requests

SAML Responses

RelayState

AuthnRequest
```

---

Replay authentication messages.

---

# 14. Intruder

Professional Version feature.

Purpose:

```text
Automated Payload Testing
```

---

Examples:

```text
Input Validation
Authorization Testing
Enumeration
```

---

# 15. Intruder Positions

Example:

```http
GET /user?id=123
```

Mark:

```text
123
```

as payload position.

---

Intruder generates:

```text
124
125
126
...
```

---

# 16. Intruder Attack Types

## Sniper

Single parameter.

---

## Battering Ram

Same payload everywhere.

---

## Pitchfork

Multiple payload lists.

---

## Cluster Bomb

All combinations.

---

Useful for:

```text
Role Testing
Parameter Testing
```

---

# 17. Sequencer

Purpose:

```text
Session Token Analysis
```

---

Burp evaluates:

```text
Randomness
Predictability
Entropy
```

---

Useful for:

```text
Session Cookies

Access Tokens
```

---

# 18. Sequencer Workflow

Capture:

```http
Set-Cookie:
JSESSIONID=...
```

---

Send:

```text
To Sequencer
```

---

Burp collects:

```text
Thousands of Samples
```

---

Produces statistical analysis.

---

# 19. Decoder

Useful for:

```text
Base64
URL Encode
JWT Parts
Hex
Unicode
```

---

Example:

```text
VGVzdA==
```

Decode:

```text
Test
```

---

# 20. Comparer

Compare:

```text
Response A

vs

Response B
```

---

Useful when:

```text
Different Users
Different Roles
Different Sessions
```

produce unexpected results.

---

# 21. Extensions

One of Burp's strongest features.

Install from:

```text
BApp Store
```

---

Popular Extensions:

```text
Autorize

JWT Editor

Logger++

Active Scan++

Retire.js

SAML Raider
```

---

# 22. SAML Raider

Extremely useful for your work.

Supports:

```text
SAML Requests
SAML Responses
XML Signatures
RelayState
```

---

Useful when analysing:

```text
PKCE + SAML
Authentication Flows
```

---

# 23. JWT Editor

Useful for:

```text
JWT Decoding
JWT Editing
JWT Signing
```

---

Inspect:

```text
Claims

Roles

Expiration
```

---

# 24. Autorize

Authorization testing plugin.

---

Workflow:

```text
Capture Admin Request

Replay As User

Compare Responses
```

---

Excellent for:

```text
Broken Access Control
```

testing.

---

# 25. Automation

Burp can automate:

```text
Target Discovery

Scanning

Testing

Reporting
```

---

Enterprise automation often uses:

```text
Burp Enterprise
```

---

# 26. Burp Enterprise

Designed for:

```text
Continuous Security Testing
```

---

Supports:

```text
Scheduling

Dashboards

Teams

Reporting
```

---

# 27. Burp In CI/CD

Workflow:

```text
Build
 ↓
Deploy
 ↓
Scan
 ↓
Report
```

---

Example:

```text
Security Gate
```

before production deployment.

---

# 28. Authentication Testing

Verify:

```text
Login
Logout
Role Changes
Session Expiration
```

---

For applications with:

```text
Creator
Publisher
Validator
Admin
```

this becomes critical.

---

# 29. Session Testing

Inspect:

```text
JSESSIONID
JWT
Refresh Tokens
```

---

Verify:

```text
Expiration

Regeneration

Logout
```

---

# 30. API Security Testing

Example:

```http
GET /api/documents
```

Test:

```http
401

403

200
```

responses.

---

Validate:

```text
Authentication

Authorization

Input Validation
```

---

# 31. Using Burp With Selenide

Flow:

```text
Selenide
 ↓
Browser
 ↓
Burp Proxy
 ↓
Application
```

---

Allows:

```text
UI Automation

+
Traffic Inspection
```

simultaneously.

---

# 32. Using Burp With RestAssured

Example:

```java
RestAssured
```

configured through Burp Proxy.

---

Inspect:

```text
Headers

Cookies

Tokens

JSON Payloads
```

---

Very useful for debugging APIs.

---

# 33. Practical Exercise

Capture:

```text
Login Request
```

through Proxy.

---

Inspect:

```text
Headers

Cookies

Response
```

---

# 34. Practical Exercise

Send request to:

```text
Repeater
```

---

Modify:

```text
Authorization Header
```

---

Observe results.

---

# 35. Practical Challenge

Perform:

```text
Publisher Login
```

---

Then:

```text
Capture Request

Replay In Repeater

Modify Token

Observe Behavior
```

---

Determine:

```text
Authentication

Authorization

Session Validation
```

---

# 36. Common Security Findings

## Broken Access Control

Example:

```text
Publisher accesses Admin Endpoint
```

---

## Weak Session Tokens

Example:

```text
Predictable IDs
```

---

## Missing Authorization

Example:

```text
200 instead of 403
```

---

## Information Disclosure

Example:

```text
Verbose Error Messages
```

---

# 37. Daily Security Routine

Every day:

1. Capture traffic.
2. Review login requests.
3. Review session cookies.
4. Test one API endpoint.
5. Replay one request.
6. Check authorization.
7. Record findings.

---

# 38. Mastery Checklist

Before proceeding to Chapter 17:

- [ ] Configure Proxy
- [ ] Use Intercept
- [ ] Use HTTP History
- [ ] Use Repeater
- [ ] Use Intruder
- [ ] Understand Sequencer
- [ ] Use Decoder
- [ ] Use Comparer
- [ ] Install Extensions
- [ ] Use SAML Raider
- [ ] Test Authentication
- [ ] Test Authorization
- [ ] Test APIs
- [ ] Integrate Burp With Automation

---

# 39. Chapter Summary

After completing this chapter you should be able to:

- Analyse web traffic effectively
- Investigate authentication flows
- Test APIs manually
- Validate authorization controls
- Identify security weaknesses
- Use Burp extensions efficiently
- Integrate Burp with automation workflows

The next chapter:

```markdown
# Chapter 17 - SAML Authentication
```

will cover:

- SAML Architecture
- Identity Providers
- Service Providers
- PKCE
- Authentication Flows
- RelayState
- AuthnRequest
- Assertions
- RestAssured Integration
- Jsoup Extraction
- Cookie Management
- AuthenticationCalls Design

# Chapter 17 - SAML Authentication

#table-of-contents

---

# 1. Introduction

SAML (Security Assertion Markup Language) is one of the most widely used enterprise authentication protocols.

Common users:

```text
Government Systems
Banking Platforms
Enterprise Applications
Identity Providers
```

Examples:

```text
Microsoft Entra ID (Azure AD)
ADFS
Okta
Keycloak
Ping Identity
```

In your current framework, SAML is particularly relevant because you've been implementing:

```text
RestAssured
PKCE
Jsoup
Session Reuse
Cookie Management
AuthenticationCalls
```

without relying on UI automation.

---

# 2. Why SAML Matters

Without SAML:

```text
Application handles login directly.
```

---

With SAML:

```text
Application
      ↓
Identity Provider
      ↓
Authentication
      ↓
Return Assertion
      ↓
Application Session
```

---

Benefits:

```text
Single Sign-On (SSO)
Federation
Centralized Authentication
Security
```

---

# 3. Core SAML Components

## Service Provider (SP)

Application being accessed.

Example:

```text
FADO
Eurosur
Internal Enterprise Portal
```

---

## Identity Provider (IdP)

Responsible for authentication.

Examples:

```text
Microsoft Entra ID
ADFS
Okta
Keycloak
```

---

## User Agent

Usually:

```text
Browser
```

In automation:

```text
RestAssured
```

---

# 4. SAML Authentication Flow

Typical flow:

```text
User
 ↓
Service Provider
 ↓
Redirect
 ↓
Identity Provider
 ↓
Login
 ↓
SAML Assertion
 ↓
Service Provider
 ↓
Session
```

---

Visual representation:

```text
Application
     ↓
Redirect
     ↓
IdP Login
     ↓
SAML Response
     ↓
Application Session
```

---

# 5. Understanding Redirects

SAML heavily relies on:

```http
302 Found
```

responses.

---

Example:

```http
GET /application
```

returns:

```http
302 Location:
https://idp.company.com
```

---

RestAssured must follow these redirects manually in many scenarios.

---

# 6. Understanding RelayState

RelayState preserves navigation context.

Example:

```text
Requested page
Requested application
Session metadata
```

---

Typical response:

```html
<input
name="RelayState"
value="xyz123" />
```

---

Must often be submitted back.

---

# 7. Understanding SAMLResponse

After successful login:

```html
<input
name="SAMLResponse"
value="...." />
```

---

It contains:

```text
Assertion
Identity
Roles
Session Information
```

encoded in Base64.

---

# 8. PKCE Overview

PKCE:

```text
Proof Key for Code Exchange
```

is commonly used with:

```text
OAuth2
OIDC
Modern Enterprise Identity Platforms
```

---

Components:

```text
Code Verifier
Code Challenge
Authorization Code
Access Token
```

---

# 9. PKCE Flow

Typical:

```text
Client
 ↓
Code Verifier
 ↓
Code Challenge
 ↓
Authorization Request
 ↓
Authorization Code
 ↓
Token Exchange
 ↓
Access Token
```

---

# 10. Why PKCE Matters In Automation

Without PKCE:

```text
Authorization Code
can be intercepted.
```

---

With PKCE:

```text
Authorization Code
useless without Verifier.
```

---

Security greatly improves.

---

# 11. RestAssured In Authentication

RestAssured allows:

```java
given()
.when()
.then()
```

requests.

---

Example:

```java
Response response =
    given()
        .redirects()
        .follow(false)
    .when()
        .get(url);
```

---

Useful when tracking:

```text
302 redirects
SAML pages
Cookies
```

---

# 12. Capturing Redirects

Example:

```java
Response response =
    given()
    .redirects()
    .follow(false)
    .when()
    .get(authenticationUrl);
```

---

Extract:

```java
String location =
    response.getHeader(
        "Location"
    );
```

---

Continue flow manually.

---

# 13. Why Follow Redirects Manually

SAML debugging becomes easier.

You can inspect:

```text
RelayState
SAMLRequest
Redirect Chain
Auth Parameters
```

---

Very useful when authentication fails.

---

# 14. Jsoup Overview

Jsoup parses HTML.

Example:

```java
Document document =
    Jsoup.parse(html);
```

---

Allows reading:

```text
Forms
Inputs
Buttons
Hidden Fields
```

---

# 15. Extracting Hidden Inputs

Example page:

```html
<input
name="SAMLResponse"
value="abc123"/>
```

---

Extract:

```java
String samlResponse =
    document
        .select(
            "input[name=SAMLResponse]"
        )
        .val();
```

---

# 16. Extracting RelayState

Example:

```java
String relayState =
    document
        .select(
            "input[name=RelayState]"
        )
        .val();
```

---

Common requirement.

---

# 17. Building Form Data

Example:

```java
Map<String, String> form =
    new HashMap<>();
```

---

Add:

```java
form.put(
    "SAMLResponse",
    samlResponse
);
```

---

Add:

```java
form.put(
    "RelayState",
    relayState
);
```

---

Submit:

```java
given()
    .formParams(form)
```

---

# 18. Cookie Management

Most authentication systems rely on:

```text
Session Cookies
```

Examples:

```text
JSESSIONID
AUTH
SESSION
```

---

# 19. Extracting Cookies

Example:

```java
Map<String, String> cookies =
    response
        .getCookies();
```

---

Store:

```java
sessionCookies
```

---

Reuse later.

---

# 20. Sending Cookies

Example:

```java
given()
    .cookies(sessionCookies)
```

---

This avoids:

```text
Repeated login
```

for every test.

---

# 21. Session Reuse

Bad:

```text
Authenticate
Authenticate
Authenticate
```

before every test.

---

Better:

```text
Authenticate once
Reuse Session
```

---

Huge performance improvement.

---

# 22. Current Framework Direction

Your authentication architecture already points towards:

```java
AuthenticationCalls
```

---

Purpose:

```text
Encapsulate Authentication
```

---

Tests remain clean.

---

# 23. AuthenticationCalls Structure

Recommended:

```java
public class AuthenticationCalls {
}
```

---

Responsibilities:

```text
Login
Cookie Management
Token Extraction
Session Handling
Redirect Processing
```

---

# 24. Recommended API

Example:

```java
String session =
    authenticationCalls
        .authenticate(
            username,
            password
        );
```

---

Usage:

```java
given()
    .cookie(
        "SESSION",
        session
    );
```

---

# 25. Advanced Version

Return:

```java
AuthenticationContext
```

instead of:

```java
String
```

---

Example:

```java
public class
AuthenticationContext {

    private Map<String,String>
        cookies;

    private String token;
}
```

---

Benefits:

```text
Future-Proof
Flexible
Reusable
```

---

# 26. Session Validation

Verify:

```java
GET /whoami
```

returns:

```http
200
```

---

instead of:

```http
401
```

---

before executing tests.

---

# 27. SAML Debugging Strategy

When authentication fails:

Verify:

```text
Redirect URL
```

Then:

```text
RelayState
```

Then:

```text
SAMLResponse
```

Then:

```text
Cookies
```

Then:

```text
Final Redirect
```

---

# 28. Common SAML Problems

## Missing RelayState

Application returns:

```text
Unauthorized
```

---

Cause:

```text
RelayState not posted back
```

---

# 29. Common SAML Problems

## SAMLResponse Missing

Cause:

```text
HTML parsing failure
```

---

Verify:

```java
Jsoup selectors
```

---

# 30. Common SAML Problems

## Cookies Lost

Cause:

```java
Response cookies
not reused
```

---

Solution:

```java
Store
Reuse
Forward
```

---

# 31. Common SAML Problems

## Redirect Loop

Symptoms:

```text
Login
Login
Login
```

---

Usually:

```text
Session invalid
```

---

or:

```text
Missing cookie
```

---

# 32. Practical Exercise

Capture:

```text
RelayState
```

using:

```java
Jsoup
```

---

Expected:

```java
document
    .select(...)
```

---

# 33. Practical Exercise

Capture:

```text
SAMLResponse
```

and submit it.

---

Verify:

```http
200
```

response.

---

# 34. Practical Exercise

Extract:

```java
response.getCookies()
```

---

Store:

```java
sessionCookies
```

---

Reuse in second request.

---

# 35. Practical Challenge

Implement:

```java
AuthenticationCalls
```

capable of:

```text
GET Authentication Page
Extract Hidden Inputs
Submit Login
Capture Session Cookie
Return AuthenticationContext
```

---

Tests should use:

```java
AuthenticationCalls
```

without knowing:

```text
SAML
PKCE
Redirects
Cookies
```

details.

---

# 36. Framework Integration

Recommended flow:

```text
@BeforeSuite
        ↓
AuthenticationCalls
        ↓
AuthenticationContext
        ↓
Session Reuse
        ↓
All Tests
```

---

Reduces:

```text
Execution Time
Authentication Complexity
Maintenance Cost
```

---

# 37. Daily Practice Routine

Every day:

1. Inspect one redirect.
2. Inspect one cookie.
3. Extract one hidden field.
4. Practice Jsoup selectors.
5. Follow one SAML flow manually.
6. Review AuthenticationCalls code.

---

# 38. Mastery Checklist

Before proceeding to Troubleshooting:

- [ ] Understand SAML Architecture
- [ ] Understand PKCE
- [ ] Follow Redirect Chains
- [ ] Use RestAssured
- [ ] Use Jsoup
- [ ] Extract RelayState
- [ ] Extract SAMLResponse
- [ ] Manage Cookies
- [ ] Reuse Sessions
- [ ] Design AuthenticationCalls
- [ ] Debug Authentication Problems
- [ ] Build AuthenticationContext

---

# 39. Chapter Summary

After completing this chapter you should be able to:

- Understand enterprise SAML authentication
- Automate authentication with RestAssured
- Parse login pages with Jsoup
- Manage cookies and sessions
- Implement AuthenticationCalls cleanly
- Remove authentication logic from tests
- Build scalable authentication solutions

The next section of the Knowledge Base starts the:

```markdown
# Part XI - Troubleshooting
```

Beginning with:

```markdown
# Chapter 18 - Neovim Troubleshooting
```

where we will document real-world problems, diagnostics, recovery procedures, and solutions collected during daily development.

# Chapter 18 - Neovim Troubleshooting

#table-of-contents

---

# 1. Introduction

This chapter documents real-world Neovim problems, diagnostics and recovery procedures.

Unlike previous chapters focused on learning, this chapter focuses on:

```text
Problem
↓
Diagnosis
↓
Root Cause
↓
Solution
↓
Prevention
```

This should become your day-to-day operational runbook.

Primary areas:

```text
LazyVim
Keymaps
Plugins
Telescope
Snacks
Mason
LSP
Performance
Terminal Integration
```

---

# 2. Troubleshooting Methodology

Always investigate in this order:

```text
1. Reproduce
2. Observe Error
3. Verify Configuration
4. Check Health
5. Check Logs
6. Apply Fix
7. Validate
```

Useful command:

```vim
:checkhealth
```

---

# 3. Keymap Not Working

## Symptoms

```text
New mapping does nothing
Wrong action executes
No error message
```

---

## Diagnosis

Verify mapping:

```vim
:map <leader>tM
```

---

Verify source:

```vim
:verbose map <leader>tM
```

Expected:

```text
Last set from:
~/.config/nvim/lua/config/keymaps.lua
```

---

## Common Causes

```text
Mapping overwritten
Configuration not reloaded
Plugin overwrote mapping
Wrong mode used
```

---

## Fix

Reload:

```vim
:lua package.loaded["config.keymaps"]=nil
```

```vim
:lua require("config.keymaps")
```

---

# 4. Keymaps.lua Changes Not Applied

## Symptoms

```text
File saved
Mapping unchanged
```

---

## Diagnosis

Check cache:

```vim
:lua print(package.loaded["config.keymaps"])
```

---

## Fix

```vim
:lua package.loaded["config.keymaps"]=nil
```

```vim
:lua require("config.keymaps")
```

---

## Alternative

Restart Neovim:

```bash
nvim
```

---

# 5. Telescope Not Working

## Symptoms

```text
:Telescope find_files fails
:Telescope live_grep fails
```

---

## Diagnosis

```vim
:checkhealth telescope
```

---

Verify plugin:

```vim
:Lazy
```

---

Search:

```text
telescope.nvim
```

---

## Fix

Sync plugins:

```vim
:Lazy sync
```

---

Update:

```vim
:Lazy update
```

---

# 6. Telescope Finds No Files

## Symptoms

```text
Empty results
```

---

## Diagnosis

Check current path:

```vim
:pwd
```

---

Verify project root:

```vim
:echo getcwd()
```

---

## Fix

Open project correctly:

```bash
nvim .
```

instead of:

```bash
nvim file.java
```

---

# 7. Snacks Terminal Does Not Open

## Symptoms

```text
Nothing happens
```

---

## Diagnosis

Verify:

```vim
:Lazy
```

---

Look for:

```text
snacks.nvim
```

---

## Fix

Install/update plugin:

```vim
:Lazy sync
```

---

# 8. Snacks Terminal Opens Then Closes

## Symptoms

```text
Terminal flashes
Immediately disappears
```

---

## Cause

```lua
auto_close = true
```

---

## Fix

```lua
Snacks.terminal(
    command,
    {
        auto_close = false
    }
)
```

---

# 9. Terminal Cannot Find Maven

## Symptoms

```text
mvn command not found
```

---

## Diagnosis

Terminal:

```bash
which mvn
```

---

Verify:

```bash
mvn -v
```

---

## Fix

Correct:

```bash
JAVA_HOME
PATH
```

configuration.

---

# 10. Neovim Startup Is Slow

## Symptoms

```text
2-10 second startup
```

---

## Diagnosis

```vim
:Lazy profile
```

---

Identify:

```text
Slow Plugins
```

---

## Fix

Disable unused plugins.

---

Use lazy loading.

---

# 11. Plugin Not Loading

## Symptoms

```text
Configuration exists
Plugin unavailable
```

---

## Diagnosis

```vim
:Lazy
```

---

Verify:

```text
Loaded
```

state.

---

## Fix

```vim
:Lazy sync
```

---

Restart:

```vim
:qa
```

---

# 12. Mason Not Working

## Symptoms

```text
:Mason opens empty
```

or:

```text
Installation fails
```

---

## Diagnosis

```vim
:checkhealth mason
```

---

## Fix

Update Mason:

```vim
:MasonUpdate
```

---

# 13. LSP Not Attaching

## Symptoms

```text
gd fails
gr fails
hover unavailable
```

---

## Diagnosis

```vim
:LspInfo
```

Expected:

```text
Client attached
```

---

## Common Cause

```text
File type mismatch
```

---

# 14. Formatting Not Working

## Symptoms

```text
Format key does nothing
```

---

## Diagnosis

```vim
:LspInfo
```

Verify formatter attached.

---

## Manual Test

```vim
:lua vim.lsp.buf.format()
```

---

# 15. Code Actions Not Appearing

## Symptoms

```text
<leader>ca shows nothing
```

---

## Diagnosis

Verify:

```vim
:LspInfo
```

Expected:

```text
jdtls
```

attached.

---

# 16. Treesitter Issues

## Symptoms

```text
Broken syntax highlighting
```

---

## Diagnosis

```vim
:TSInstallInfo
```

---

## Fix

Install parser:

```vim
:TSInstall java
```

---

Update:

```vim
:TSUpdate
```

---

# 17. Neovim Consumes Too Much Memory

## Symptoms

```text
Slow editor
High RAM usage
```

---

## Diagnosis

```vim
:Lazy profile
```

---

Look for:

```text
Heavy Plugins
```

---

# 18. File Explorer Issues

## Symptoms

```text
Explorer empty
```

or:

```text
Cannot rename files
```

---

## Diagnosis

Check plugin:

```text
neo-tree
```

or:

```text
oil.nvim
```

depending on setup.

---

## Fix

Reload plugin.

---

# 19. Clipboard Not Working

## Symptoms

```text
Yank
Paste fails outside Neovim
```

---

## Diagnosis

```vim
:echo has("clipboard")
```

Expected:

```text
1
```

---

## Fix

Use:

```vim
"+y
```

---

Verify:

```bash
xclip
```

or:

```bash
wl-copy
```

installed.

---

# 20. Search Is Extremely Slow

## Symptoms

```text
live_grep hangs
```

---

## Diagnosis

Verify:

```bash
rg --version
```

---

Required:

```text
ripgrep
```

---

Install:

```bash
sudo apt install ripgrep
```

---

# 21. Harpoon Not Working

## Symptoms

```text
Markers disappear
```

---

## Diagnosis

Verify:

```vim
:Lazy
```

Harpoon loaded.

---

## Fix

Update:

```vim
:Lazy sync
```

---

# 22. Configuration Completely Broken

## Symptoms

```text
Startup errors
```

---

## Diagnosis

Start clean:

```bash
nvim --clean
```

---

If clean works:

```text
Configuration issue
```

---

# 23. Useful Debug Commands

Health:

```vim
:checkhealth
```

---

Plugins:

```vim
:Lazy
```

---

LSP:

```vim
:LspInfo
```

---

Messages:

```vim
:messages
```

---

Current filetype:

```vim
:set filetype?
```

---

Current directory:

```vim
:pwd
```

---

# 24. Recovery Procedure

If everything fails:

## Step 1

Backup:

```text
~/.config/nvim
```

---

## Step 2

Start clean:

```bash
nvim --clean
```

---

## Step 3

Update plugins:

```vim
:Lazy sync
```

---

## Step 4

Update Mason:

```vim
:MasonUpdate
```

---

## Step 5

Restart.

---

# 25. Daily Maintenance Routine

Every week:

1. Update plugins.
2. Update Treesitter.
3. Update Mason.
4. Verify JDTLS.
5. Verify DAP.
6. Check startup time.
7. Clean unused plugins.

---

# 26. Troubleshooting Checklist

When something breaks:

- [ ] Run `:checkhealth`
- [ ] Run `:messages`
- [ ] Verify current directory
- [ ] Verify filetype
- [ ] Verify plugin loaded
- [ ] Verify LSP attached
- [ ] Reload keymaps
- [ ] Update plugins
- [ ] Try `nvim --clean`

---

# 27. Chapter Summary

After completing this chapter you should be able to:

- Diagnose most Neovim problems quickly
- Fix keymaps issues
- Recover broken plugins
- Troubleshoot Telescope
- Troubleshoot Mason
- Troubleshoot Snacks Terminal
- Diagnose performance issues
- Recover a broken configuration

The next chapter:

```markdown
# Chapter 19 - JDTLS Troubleshooting
```

will cover:

- Java Project Issues
- Language Server Issues
- Imports
- Code Actions
- Workspace Problems
- Lombok
- Maven Integration
- JDTLS Cache Problems
- Advanced Diagnostics

# Chapter 19 - JDTLS Troubleshooting

#table-of-contents

---

# 1. Introduction

This chapter focuses on troubleshooting:

```text
JDTLS
Java LSP
Code Actions
Imports
Maven Projects
Java Navigation
Refactoring
Debug Integration
```

The goal is to diagnose and recover Java development functionality as quickly as possible.

---

# 2. Troubleshooting Methodology

Always investigate in this order:

```text
1. Verify JDTLS
2. Verify Maven
3. Verify Workspace
4. Verify Code Actions
5. Verify Project Dependencies
6. Verify Cache
7. Verify Debug Adapters
```

Useful commands:

```vim
:LspInfo
```

```vim
:checkhealth
```

```vim
:Mason
```

---

# 3. JDTLS Not Detected

## Symptoms

```text
gd does nothing

gr does nothing

K does nothing

No autocomplete

No diagnostics
```

---

## Diagnosis

Run:

```vim
:LspInfo
```

Expected:

```text
Client: jdtls
```

Example:

```text
Attached clients:
- jdtls
```

---

## Common Causes

```text
JDTLS not installed
Project not recognized
Workspace corrupted
Wrong filetype
```

---

## Fix

Verify:

```vim
:Mason
```

Expected:

```text
jdtls
```

Installed.

---

Install if missing:

```vim
:MasonInstall jdtls
```

---

Restart Neovim.

---

# 4. gd Does Not Work

## Symptoms

Cursor on:

```java
goToDetailsOfMainRecipient()
```

Execute:

```vim
gd
```

Nothing happens.

---

## Diagnosis

Verify:

```vim
:LspInfo
```

---

Verify current file type:

```vim
:set filetype?
```

Expected:

```text
java
```

---

## Fix

Open project root:

```bash
nvim .
```

instead of:

```bash
nvim SomeClass.java
```

---

# 5. Imports Not Updating

## Symptoms

Unused imports remain.

Missing imports not suggested.

---

## Diagnosis

Execute:

```vim
<leader>ca
```

Expected:

```text
Organize Imports
```

---

## Common Causes

```text
JDTLS not attached

Project not indexed

Compilation errors
```

---

## Fix

Execute:

```vim
<leader>ca
```

Select:

```text
Organize Imports
```

---

Verify Maven builds:

```bash
mvn compile
```

---

# 6. Auto Import Not Working

## Symptoms

Typing:

```java
ArrayList
```

does not suggest:

```java
import java.util.ArrayList;
```

---

## Diagnosis

Verify:

```vim
:LspInfo
```

---

Verify completion works.

---

## Fix

Ensure project compiles:

```bash
mvn compile
```

---

Restart JDTLS.

---

# 7. Override Method Does Not Work

## Symptoms

Executing:

```vim
<leader>ca
```

No:

```text
Override Methods
```

option appears.

---

## Diagnosis

Verify:

```vim
:LspInfo
```

Expected:

```text
jdtls
```

attached.

---

## Fix

Execute:

```vim
<leader>ca
```

Select:

```text
Override Methods
```

---

If not available:

```bash
mvn compile
```

must succeed.

---

# 8. Implement Methods Does Not Work

## Symptoms

Class implements interface.

No:

```text
Implement Methods
```

available.

---

## Example

```java
public class UserService
implements IUserService {
}
```

---

## Diagnosis

Verify interface resolves.

Test:

```vim
gd
```

on:

```java
IUserService
```

---

## Fix

Correct compilation failures first.

---

# 9. Maven Project Does Not Load

## Symptoms

```text
Missing classes

Missing packages

Dependencies unresolved
```

---

## Diagnosis

Verify:

```bash
mvn compile
```

---

Expected:

```text
BUILD SUCCESS
```

---

If:

```text
BUILD FAILURE
```

JDTLS usually fails too.

---

## Fix

Resolve Maven compilation issues first.

---

# 10. Maven Dependencies Missing

## Symptoms

```java
Cannot resolve symbol
```

for:

```java
TestNG
Selenide
RestAssured
```

---

## Diagnosis

Execute:

```bash
mvn dependency:tree
```

---

Verify dependency exists.

---

## Fix

Force refresh:

```bash
mvn clean install -U
```

---

# 11. Classes Not Resolved

## Symptoms

```java
Cannot resolve symbol
```

despite valid code.

---

## Diagnosis

Verify:

```vim
:LspInfo
```

---

Check:

```bash
mvn compile
```

---

## Common Cause

Corrupted JDTLS cache.

---

## Fix

Remove cache:

```bash
rm -rf ~/.cache/jdtls
```

---

Restart:

```bash
nvim .
```

---

Allow reindexing.

---

# 12. Workspace Corruption

## Symptoms

```text
Random Java errors

Missing classes

Broken navigation
```

---

## Diagnosis

JDTLS behaves inconsistently.

---

## Fix

Delete:

```bash
rm -rf ~/.cache/jdtls
```

---

Reopen project.

---

Wait for:

```text
Workspace indexing
```

to complete.

---

# 13. Autocomplete Not Working

## Symptoms

No:

```text
Completion Menu
```

appears.

---

## Diagnosis

Verify:

```vim
:LspInfo
```

---

Verify completion plugin loaded.

---

Example:

```vim
:Lazy
```

Check:

```text
blink.cmp

or

nvim-cmp
```

---

## Fix

Reload plugin.

Restart Neovim.

---

# 14. Refactor Rename Not Working

## Symptoms

Execute:

```vim
<leader>cr
```

No rename operation.

---

## Diagnosis

Verify:

```vim
:LspInfo
```

---

Check symbol resolves:

```vim
gd
```

must work.

---

## Fix

Repair JDTLS connection.

---

# 15. Workspace Symbols Not Working

## Symptoms

```vim
:Telescope lsp_workspace_symbols
```

returns nothing.

---

## Diagnosis

Verify indexing completed.

---

## Fix

Recompile:

```bash
mvn compile
```

---

Restart Neovim.

---

# 16. Hover Documentation Not Working

## Symptoms

Press:

```vim
K
```

Nothing appears.

---

## Diagnosis

Verify:

```vim
:LspInfo
```

---

Verify cursor is on Java symbol.

---

## Fix

Reconnect JDTLS.

---

# 17. Lombok Not Working

## Symptoms

Errors:

```java
getUsername()
```

not found.

Despite:

```java
@Getter
```

existing.

---

## Diagnosis

Verify:

```xml
<dependency>
    <groupId>
        org.projectlombok
    </groupId>
</dependency>
```

---

Verify:

```text
lombok.jar
```

configured for JDTLS.

---

## Fix

Configure Lombok agent.

Restart JDTLS.

---

# 18. Generated Methods Missing

## Symptoms

Builder methods appear missing.

Generated getters unavailable.

---

## Diagnosis

Usually:

```text
Lombok issue
```

or:

```text
Compilation issue
```

---

## Fix

Verify:

```bash
mvn compile
```

---

Verify Lombok configuration.

---

# 19. JavaTestDebugCurrentMethod Missing

## Symptoms

Command:

```vim
:JavaTestDebugCurrentMethod
```

fails.

---

## Diagnosis

Verify:

```vim
:Mason
```

Installed:

```text
java-debug-adapter

java-test
```

---

## Fix

Install:

```vim
:MasonInstall java-debug-adapter
```

---

Install:

```vim
:MasonInstall java-test
```

---

Restart Neovim.

---

# 20. JavaTestRunCurrentMethod Missing

## Symptoms

```vim
:JavaTestRunCurrentMethod
```

unknown command.

---

## Diagnosis

Verify:

```text
java-test
```

installed.

---

## Fix

Install:

```vim
:MasonInstall java-test
```

---

# 21. Code Actions Missing

## Symptoms

```vim
<leader>ca
```

opens empty menu.

---

## Diagnosis

Verify:

```vim
:LspInfo
```

---

Confirm:

```text
jdtls attached
```

---

## Fix

Rebuild project.

Restart JDTLS.

---

# 22. Java File Opens As Plain Text

## Symptoms

```vim
:set filetype?
```

returns:

```text
text
```

---

## Fix

Force:

```vim
:set filetype=java
```

---

Investigate filetype detection.

---

# 23. Slow Java Performance

## Symptoms

```text
Autocomplete slow

Navigation slow

High CPU
```

---

## Diagnosis

Check project size.

Monitor:

```bash
top
```

or:

```bash
htop
```

---

## Fix

Clear cache.

Increase JVM memory.

---

# 24. Useful Diagnostics Commands

LSP:

```vim
:LspInfo
```

---

Health:

```vim
:checkhealth
```

---

Mason:

```vim
:Mason
```

---

Maven:

```bash
mvn compile
```

---

Dependencies:

```bash
mvn dependency:tree
```

---

Cache cleanup:

```bash
rm -rf ~/.cache/jdtls
```

---

# 25. Recovery Procedure

When Java tooling becomes unreliable:

## Step 1

Compile:

```bash
mvn compile
```

---

## Step 2

Delete cache:

```bash
rm -rf ~/.cache/jdtls
```

---

## Step 3

Restart Neovim.

---

## Step 4

Wait for indexing.

---

## Step 5

Verify:

```vim
:LspInfo
```

---

# 26. Daily Maintenance Routine

Every week:

1. Run `mvn compile`
2. Update Mason packages
3. Update plugins
4. Verify JDTLS
5. Verify code actions
6. Verify debug commands
7. Clear cache if necessary

---

# 27. Troubleshooting Checklist

When Java support breaks:

- [ ] Run `:LspInfo`
- [ ] Verify `jdtls`
- [ ] Run `mvn compile`
- [ ] Verify dependencies
- [ ] Verify filetype
- [ ] Verify Mason packages
- [ ] Clear JDTLS cache
- [ ] Restart Neovim
- [ ] Test `gd`
- [ ] Test `<leader>ca`

---

# 28. Chapter Summary

After completing this chapter you should be able to:

- Diagnose JDTLS issues quickly
- Restore Java navigation
- Fix code actions
- Resolve import problems
- Repair workspace corruption
- Troubleshoot Lombok
- Recover debugging integration
- Maintain a stable Java development environment

The next chapter:

```markdown
# Chapter 20 - Debugging Troubleshooting
```

will focus on:

- DAP failures
- Maven Debug issues
- Breakpoints ignored
- Attach failures
- Missing variables
- DAP UI problems
- Java debug adapters
- Advanced debugging recovery procedures

# Chapter 20 - Debugging Troubleshooting

#table-of-contents

---

# 1. Introduction

This chapter focuses on diagnosing and resolving problems related to:

```text
nvim-dap
nvim-dap-ui
JDTLS Debugging
java-debug-adapter
java-test
Maven Debug
TestNG Debugging
Remote JVM Debugging
```

Unlike previous debugging chapters, this chapter is focused on:

```text
Problem
↓

Diagnosis
↓

Root Cause

↓

Solution

↓

Prevention
```

This chapter should become your debugging recovery runbook.

---

# 2. Debugging Diagnostic Workflow

When debugging fails:

```text
1. Verify Maven
2. Verify JDTLS
3. Verify DAP
4. Verify Port
5. Verify Breakpoints
6. Verify Variables
7. Verify Debug Session
```

Useful commands:

```vim
:LspInfo
```

```vim
:Mason
```

```bash
mvnDebug test
```

```bash
netstat -ano | grep 8000
```

---

# 3. Breakpoint Ignored

## Symptoms

```text
Breakpoint exists

Debugger attached

Execution never stops
```

---

## Diagnosis

Verify project compiles:

```bash
mvn clean test
```

---

Verify breakpoint location:

```java
.goToDetailsOfImportantInformationPage()
```

rather than:

```java
@Test
```

annotation line.

---

## Common Causes

```text
Old binaries
Wrong module
Wrong class
Wrong profile
Stale Maven output
```

---

## Fix

Rebuild:

```bash
mvn clean test
```

---

Restart debug session.

---

Verify:

```java
Class being executed
=
Class being edited
```

---

# 4. Attach Does Not Work

## Symptoms

```text
Debugger waits forever

F5 does nothing

DAP session never starts
```

---

## Diagnosis

Verify debug port:

```bash
netstat -ano | grep 8000
```

Expected:

```text
8000 LISTENING
```

---

## Common Causes

```text
No mvnDebug running

Wrong port

Firewall

Wrong DAP configuration
```

---

## Fix

Launch:

```bash
mvnDebug test
```

before attaching.

---

Verify:

```lua
port = 8000
```

matches configuration.

---

# 5. Port 8000 Does Not Exist

## Symptoms

```text
No service listening

Connection refused
```

---

## Diagnosis

Run:

```bash
netstat -ano | grep 8000
```

No result returned.

---

## Fix

Start Maven:

```bash
mvnDebug test
```

Expected:

```text
Listening for transport dt_socket
at address: 8000
```

---

# 6. Maven Appears Frozen

## Symptoms

```text
Nothing happens

No tests run
```

---

Output:

```text
Listening for transport dt_socket
at address: 8000
```

---

## Explanation

This is normal.

Maven is waiting for:

```text
Debugger Attachment
```

---

## Solution

Attach:

```vim
F5
```

or:

```lua
require("dap").continue()
```

---

After attachment:

```text
Execution starts
```

---

# 7. DAP UI Does Not Open

## Symptoms

```text
Debug works

No Variables

No Watches

No Call Stack
```

---

## Diagnosis

Verify:

```lua
require("dapui")
```

does not throw an error.

---

## Fix

Open manually:

```lua
require("dapui").open()
```

---

Verify installation:

```vim
:Lazy
```

Expected:

```text
nvim-dap-ui
```

Loaded.

---

# 8. DAP UI Opens Empty

## Symptoms

```text
UI visible

No data displayed
```

---

## Cause

Debugger not stopped at breakpoint.

---

## Fix

Set breakpoint:

```vim
F9
```

---

Stop execution.

---

Variables appear only when execution pauses.

---

# 9. Variables Do Not Appear

## Symptoms

```text
Variables panel empty
```

---

## Diagnosis

Open:

```lua
require("dapui").open()
```

---

Verify:

```text
Debugger paused
```

---

## Fix

Place breakpoint.

Stop execution.

Inspect:

```java
mainRecipientName

expectedValuesHBDetails

actualValuesHBDetails
```

---

# 10. Watches Not Updating

## Symptoms

```text
Watch exists

Value never changes
```

---

## Cause

Expression invalid.

---

## Fix

Use:

```java
mainRecipientName
```

instead of:

```java
this.mainRecipientName
```

if not available in scope.

---

# 11. JavaTestDebugCurrentMethod Missing

## Symptoms

```vim
:JavaTestDebugCurrentMethod
```

returns:

```text
Not an editor command
```

---

## Diagnosis

Check:

```vim
:Mason
```

Expected:

```text
java-debug-adapter

java-test
```

---

## Fix

Install:

```vim
:MasonInstall java-debug-adapter
```

---

Install:

```vim
:MasonInstall java-test
```

---

Restart Neovim.

---

# 12. JavaTestRunCurrentMethod Missing

## Symptoms

```vim
:JavaTestRunCurrentMethod
```

unknown command.

---

## Diagnosis

Verify:

```text
java-test
```

package installed.

---

## Fix

Install:

```vim
:MasonInstall java-test
```

---

# 13. Debug Commands Exist But Do Nothing

## Symptoms

```text
Commands execute

Nothing launches
```

---

## Diagnosis

Verify:

```vim
:LspInfo
```

Expected:

```text
jdtls
```

---

## Fix

Reconnect:

```vim
:LspRestart
```

or restart Neovim.

---

# 14. DAP Continue Fails

## Symptoms

```lua
require("dap").continue()
```

does not attach.

---

## Diagnosis

Inspect configuration:

```lua
require("dap")
    .configurations
    .java
```

---

Verify:

```lua
hostName = "127.0.0.1"
port = 8000
```

---

## Fix

Correct configuration.

---

# 15. Breakpoint Set But Grey

## Symptoms

```text
Grey breakpoint
```

---

## Cause

Source not loaded by debugger.

---

## Fix

Verify:

```java
Correct Class
Correct Module
Correct Source
```

---

Rebuild Maven.

---

# 16. Step Into Does Not Enter Method

## Symptoms

```vim
F11
```

jumps unexpectedly.

---

## Cause

Method:

```java
JDK internal

Library call
```

---

## Example

```java
String.valueOf()
```

---

Expected behaviour.

---

# 17. Debug Session Terminates Immediately

## Symptoms

```text
Attach succeeds

Session closes immediately
```

---

## Cause

Test finished before debugger attached.

---

## Fix

Use:

```java
@BeforeMethod
```

breakpoint.

---

Attach earlier.

---

# 18. XML Suite Debug Fails

## Symptoms

```bash
mvnDebug test \
-DsuiteXmlFile=...
```

starts but classes never execute.

---

## Diagnosis

Verify XML:

```xml
<class name="..." />
```

---

Verify:

```bash
mvn test
```

works without debug.

---

# 19. Debugging Parallel Tests

## Symptoms

```text
Breakpoints hit randomly
```

---

## Cause

Parallel execution.

---

## Diagnosis

Check:

```xml
parallel="tests"
```

or:

```xml
parallel="classes"
```

---

## Fix

Temporarily disable:

```xml
parallel="false"
```

while debugging.

---

# 20. Debugging Wrong User

## Symptoms

```text
Unexpected permissions
```

---

## Diagnosis

Breakpoint:

```java
login()
```

Inspect:

```java
username
```

---

Verify expected role:

```text
Publisher
Creator
Validator
```

---

# 21. Maven Uses Wrong Profile

## Symptoms

```text
Different behaviour
than expected
```

---

## Diagnosis

Execute:

```bash
mvn help:active-profiles
```

---

## Fix

Specify explicitly:

```bash
mvnDebug test -Ppublisher
```

---

# 22. JDTLS Debug Integration Broken

## Symptoms

```text
Run works

Debug doesn't
```

---

## Diagnosis

Verify:

```vim
:Mason
```

Contains:

```text
java-debug-adapter
```

---

## Fix

Reinstall package.

Restart Neovim.

---

# 23. Useful Debug Commands

Check LSP:

```vim
:LspInfo
```

---

Check Mason:

```vim
:Mason
```

---

Open DAP UI:

```lua
require("dapui").open()
```

---

Close DAP UI:

```lua
require("dapui").close()
```

---

Terminate:

```lua
require("dap").terminate()
```

---

Breakpoint:

```lua
require("dap").toggle_breakpoint()
```

---

# 24. Full Recovery Procedure

When debugging completely breaks:

## Step 1

Verify Maven:

```bash
mvn clean test
```

---

## Step 2

Verify JDTLS:

```vim
:LspInfo
```

---

## Step 3

Verify Mason:

```vim
:Mason
```

---

## Step 4

Verify:

```text
java-debug-adapter
```

---

## Step 5

Verify:

```text
java-test
```

---

## Step 6

Restart Neovim.

---

## Step 7

Launch:

```bash
mvnDebug test
```

---

## Step 8

Attach DAP.

---

# 25. Daily Debug Validation

Verify weekly:

- [ ] DAP works
- [ ] DAP UI works
- [ ] Breakpoints work
- [ ] Variables appear
- [ ] Watches work
- [ ] JavaTestDebugCurrentMethod works
- [ ] Maven Debug works
- [ ] XML Suite Debug works

---

# 26. Troubleshooting Checklist

When debugging breaks:

- [ ] Verify Maven build
- [ ] Verify JDTLS
- [ ] Verify DAP
- [ ] Verify port 8000
- [ ] Verify breakpoint location
- [ ] Verify DAP UI
- [ ] Verify variables panel
- [ ] Verify java-test
- [ ] Verify java-debug-adapter
- [ ] Restart session

---

# 27. Chapter Summary

After completing this chapter you should be able to:

- Diagnose DAP failures
- Diagnose Maven Debug failures
- Recover broken debug sessions
- Fix attach problems
- Fix breakpoint issues
- Recover missing variables
- Troubleshoot XML suite debugging
- Understand the full Java debug stack

The next chapter:

```markdown
# Chapter 21 - Selenide Troubleshooting
```

will focus on:

- Element Not Found
- Element Not Visible
- Stale Elements
- Empty Collections
- File Downloads
- Timeouts
- Flaky Tests
- Browser Configuration
- Locator Recovery Strategies
- Real Selenide Production Issues

# Chapter 21 - Selenide Troubleshooting

#table-of-contents

---

# 1. Introduction

This chapter focuses on diagnosing and resolving problems related to:

```text
Selenide
Selenium
UI Automation
Locators
Waits
ElementsCollection
Downloads
Browser Configuration
Flaky Tests
```

The goal is to create a practical troubleshooting runbook for daily automation work.

---

# 2. Troubleshooting Methodology

When a UI test fails:

```text
1. Verify Locator
2. Verify Visibility
3. Verify Timing
4. Verify Page State
5. Verify Browser State
6. Debug Collection Contents
7. Compare HTML
```

Useful techniques:

```java
getText()
```

```java
scrollIntoView(true)
```

```java
rows.size()
```

```java
Screenshots.takeScreenShotAsFile();
```

---

# 3. Element Not Found

## Symptoms

```text
Element not found
```

Example:

```java
Element not found
{#save-button}
```

---

## Diagnosis

Verify element eventually appears.

Use:

```java
SAVE_BUTTON.shouldBe(
    Condition.visible
);
```

---

## Common Causes

```text
Wrong locator

Wrong page

Element not loaded

Timing issue
```

---

## Fix

Replace:

```java
SAVE_BUTTON.click();
```

with:

```java
SAVE_BUTTON
    .shouldBe(
        Condition.visible
    )
    .click();
```

---

# 4. Element Not Visible

## Symptoms

```text
Element exists

Click fails
```

---

## Diagnosis

Verify visibility:

```java
element.isDisplayed();
```

---

Or:

```java
element.shouldBe(
    Condition.visible
);
```

---

## Fix

Scroll first:

```java
element.scrollIntoView(true);
```

---

Then:

```java
element.click();
```

---

## Common Causes

```text
Collapsed sections

Off-screen elements

Hidden tabs

Unfinished loading
```

---

# 5. Element Is Not Clickable

## Symptoms

```text
ElementClickInterceptedException
```

---

## Causes

```text
Loading spinner

Modal

Overlay

Toast notification
```

---

## Diagnosis

Inspect page manually.

Use screenshot.

---

## Fix

Wait for overlay:

```java
LOADER.shouldDisappear();
```

---

Then click.

---

# 6. Collection Empty

## Symptoms

```java
rows.size() == 0
```

---

## Diagnosis

Debug:

```java
rows.size()
```

---

Example:

```java
ElementsCollection rows =
    $$("tr");
```

---

Verify Table Appears:

```java
TABLE.shouldBe(
    Condition.visible
);
```

---

## Common Causes

```text
Table not loaded

Wrong page

Wrong locator

Search returned no data
```

---

# 7. Collection Size Unexpected

## Symptoms

Expected:

```text
10 rows
```

Actual:

```text
2 rows
```

---

## Diagnosis

Inspect:

```java
rows.get(0).getText()
```

---

Inspect:

```java
rows.get(1).getText()
```

---

Debug using DAP.

---

# 8. Stale Element Reference

## Symptoms

```text
StaleElementReferenceException
```

---

## Cause

Page refreshed.

Element became invalid.

---

## Wrong

```java
SelenideElement row =
    $("tr");

refresh();

row.click();
```

---

## Correct

Re-locate:

```java
$("tr").click();
```

---

Or:

```java
row =
    $("tr");
```

again.

---

# 9. Browser Closes Unexpectedly

## Symptoms

```text
Browser closes after execution
```

---

## Diagnosis

Verify:

```java
Configuration.holdBrowserOpen
```

---

## Fix

Development only:

```java
Configuration.holdBrowserOpen =
    true;
```

---

Avoid in CI/CD.

---

# 10. Browser Never Opens

## Symptoms

```text
Test starts

No browser
```

---

## Diagnosis

Check:

```java
Configuration.browser
```

---

Verify:

```bash
java -version
```

---

Verify driver.

---

## Fix

Check browser installation.

---

# 11. Download Fails

## Symptoms

```text
File never downloaded
```

---

## Diagnosis

Verify:

```java
Configuration.fileDownload
```

---

Expected:

```java
PROXY
```

or:

```java
FOLDER
```

---

## Fix

Example:

```java
Configuration.fileDownload =
    FileDownloadMode.PROXY;
```

---

# 12. Upload Fails

## Symptoms

```text
File not uploaded
```

---

## Diagnosis

Verify:

```java
uploadFile(...)
```

path exists.

---

## Fix

Use:

```java
new File(...)
```

with full path.

---

# 13. Flaky Tests

## Symptoms

```text
Pass sometimes

Fail sometimes
```

---

Most common causes:

```text
Thread.sleep()

Timing issues

Shared data

Environment instability
```

---

# 14. Remove Thread.sleep()

Bad:

```java
Thread.sleep(5000);
```

---

Good:

```java
SAVE_BUTTON.shouldBe(
    Condition.visible
);
```

---

Better:

```java
SUCCESS_MESSAGE
    .shouldHave(
        Condition.text(
            "Saved"
        )
    );
```

---

# 15. Timeout Exceeded

## Symptoms

```text
TimeoutException
```

---

## Diagnosis

Verify:

```java
Configuration.timeout
```

---

Example:

```java
4000
```

may be too small.

---

## Fix

Increase:

```java
Configuration.timeout =
    15000;
```

---

Only when justified.

---

# 16. Wrong Page Loaded

## Symptoms

```text
Locator missing

Navigation fails
```

---

## Diagnosis

Validate page:

```java
waitForPageToLoad();
```

---

Verify page title.

---

Verify unique page element.

---

# 17. XPath Stopped Working

## Symptoms

```java
$x(...)
```

no longer finds element.

---

## Diagnosis

Compare:

```text
Current HTML
```

vs

```text
Previous HTML
```

---

## Common Causes

```text
Frontend changed

Additional wrappers

React update
```

---

# 18. XPath Recovery Strategy

Bad:

```java
/html/body/div[1]/...
```

---

Better:

```java
//button[text()='Save']
```

---

Best:

```java
//button[
contains(@data-testid,'save')
]
```

---

# 19. ElementsCollection Lookup Fails

## Symptoms

```java
rows.findBy(...)
```

returns nothing.

---

## Diagnosis

Print:

```java
rows.texts()
```

---

Verify text actually exists.

---

## Fix

Use:

```java
Condition.partialText(...)
```

if values changed.

---

# 20. Screenshots Missing

## Symptoms

```text
No screenshots generated
```

---

## Diagnosis

Verify reports directory.

---

Generate manually:

```java
Screenshots
    .takeScreenShotAsFile();
```

---

## Fix

Ensure test framework captures failures.

---

# 21. Dynamic Tables

## Symptoms

```java
rows.first()
```

returns unexpected row.

---

## Cause

Sorting changed.

Data changed.

---

## Fix

Search by content:

```java
rows.findBy(
    Condition.text(
        expectedValue
    )
);
```

---

# 22. Main Recipient Example

Instead of:

```java
rows.get(0)
```

Prefer:

```java
rows.findBy(
    Condition.text(
        mainRecipientName
    )
);
```

---

More reliable.

---

# 23. Modal Dialog Issues

## Symptoms

```text
Element hidden behind modal
```

---

## Diagnosis

Verify:

```java
MODAL.shouldBe(
    Condition.visible
);
```

---

## Fix

Wait modal.

Interact only afterwards.

---

# 24. Loading Spinner Never Disappears

## Symptoms

```text
Tests hang
```

---

## Diagnosis

Inspect:

```java
LOADER
```

---

## Fix

Use:

```java
LOADER.shouldDisappear();
```

---

# 25. Wrong User Permissions

## Symptoms

```text
Button not visible
```

---

## Cause

User role.

Not UI problem.

---

## Diagnosis

Verify:

```text
Creator
Publisher
Validator
Admin
```

used in test.

---

# 26. Useful Debug Techniques

Breakpoint:

```java
getText(...)
```

---

Inspect:

```java
element

rows

text
```

---

Capture screenshot:

```java
Screenshots
    .takeScreenShotAsFile();
```

---

Save page source:

```java
Configuration.savePageSource =
    true;
```

---

# 27. Recovery Procedure

When a test suddenly breaks:

## Step 1

Take screenshot.

---

## Step 2

Save page source.

---

## Step 3

Verify locator.

---

## Step 4

Verify visibility.

---

## Step 5

Verify role.

---

## Step 6

Compare HTML.

---

## Step 7

Debug collection contents.

---

# 28. Daily Maintenance Routine

Every week:

1. Remove sleeps.
2. Review XPaths.
3. Review failed tests.
4. Review collections.
5. Review visibility checks.
6. Refactor flaky tests.
7. Capture screenshots on failures.

---

# 29. Troubleshooting Checklist

When a Selenide test fails:

- [ ] Verify locator
- [ ] Verify element visible
- [ ] Verify page loaded
- [ ] Verify collection size
- [ ] Verify user role
- [ ] Verify timeout
- [ ] Verify browser configuration
- [ ] Verify downloads
- [ ] Verify uploads
- [ ] Compare HTML

---

# 30. Chapter Summary

After completing this chapter you should be able to:

- Diagnose locator failures
- Diagnose wait problems
- Troubleshoot collections
- Fix flaky tests
- Recover broken XPath locators
- Handle downloads and uploads
- Debug UI failures efficiently
- Improve overall framework stability

The next chapter:

```markdown
# Chapter 22 - Generics Troubleshooting
```

will focus on:

- Bounds Mismatch
- Return Type Errors
- Self Referencing Generic Issues
- Fluent API Problems
- Generic Interfaces
- Builder Failures
- Compilation Diagnostics
- CMDetailsPage<T> Troubleshooting

# Chapter 22 - Generics Troubleshooting

#table-of-contents

---

# 1. Introduction

This chapter focuses on diagnosing and fixing compilation problems related to:

```java
CMDetailsPage<T>
```

and:

```java
IGenericMethods<T>
```

The majority of generic-related errors in automation frameworks are caused by:

```text
Wrong Bounds
Wrong Return Types
Object Instead Of T
Self Referencing Generic Mistakes
Interface Mismatches
Unsafe Casting
```

This chapter is based on real problems commonly found in Page Object frameworks that use:

```java
CMDetailsPage<T extends CMDetailsPage<T>>
```

---

# 2. Troubleshooting Methodology

Whenever a generic compilation error occurs:

```text
1. Read the Generic Type
2. Read the Generic Bound
3. Find Returned Type
4. Verify Interface Contract
5. Verify Child Class Declaration
6. Verify Fluent Methods
7. Verify Casts
```

Always identify:

```text
Expected Type
```

and:

```text
Actual Type
```

---

# 3. Return Type Incompatible

## Error

```text
return type incompatible with T
```

---

## Example

Wrong:

```java
@Override
public Object getInstance() {

    return this;
}
```

---

Expected:

```java
@Override
public T getInstance() {

    return getInstance();
}
```

---

Compiler sees:

```text
Expected:
T

Actual:
Object
```

---

## Fix

Return:

```java
T
```

instead of:

```java
Object
```

---

Correct:

```java
@Override
public T getInstance() {

    return (T) this;
}
```

---

# 4. Wrong Return Type In Fluent APIs

## Symptoms

Method chaining fails.

---

Example:

```java
page
    .clickEdit()
    .save();
```

Compilation error.

---

Cause:

```java
clickEdit()
```

returns:

```java
Object
```

---

Wrong:

```java
public Object clickEdit() {

    click(BTN_EDIT);

    return this;
}
```

---

Correct:

```java
public T clickEdit() {

    click(BTN_EDIT);

    return getInstance();
}
```

---

# 5. Bound Mismatch

## Error

```text
type argument is not within bounds
```

---

One of the most common generic errors.

---

# 6. Example Of Wrong Bound

Wrong:

```java
CMDetailsPage<CMDetailsPage>
```

---

Compiler reports:

```text
type argument not within bounds
```

---

Reason:

```java
CMDetailsPage
```

does not satisfy:

```java
T extends CMDetailsPage<T>
```

---

# 7. Correct Bound

Parent:

```java
public abstract class
CMDetailsPage<
    T extends CMDetailsPage<T>
>
```

---

Child:

```java
public class HBDetailsPage
extends
CMDetailsPage<
    HBDetailsPage
>
```

---

Child type becomes:

```java
T
```

inside parent methods.

---

# 8. Understanding Self Referencing Bounds

Pattern:

```java
T extends CMDetailsPage<T>
```

means:

```text
Any child type

must itself extend

CMDetailsPage<ThatChild>
```

---

Examples:

Valid:

```java
HBDetailsPage
```

---

Valid:

```java
LegalInformationDetailsPage
```

---

Invalid:

```java
String
```

---

Invalid:

```java
Object
```

---

# 9. Child Class Not Compiling

## Error

```text
cannot infer type arguments
```

or:

```text
type parameter mismatch
```

---

Wrong:

```java
public class HBDetailsPage
extends CMDetailsPage {
}
```

---

Correct:

```java
public class HBDetailsPage
extends CMDetailsPage<
    HBDetailsPage
> {
}
```

---

# 10. Generic Interface Not Compiling

## Error

```text
Method does not override
```

---

Interface:

```java
public interface
IGenericMethods<T> {

    T getInstance();
}
```

---

Implementation:

Wrong:

```java
public Object getInstance()
```

---

Correct:

```java
public T getInstance()
```

---

# 11. Interface And Implementation Mismatch

Wrong:

```java
public interface
IGenericMethods<T> {

    T getInstance();
}
```

---

Implementation:

```java
@Override
public Object getInstance()
```

---

Compiler:

```text
Method does not implement
method from interface
```

---

Fix:

Match signatures exactly.

---

# 12. Cast Warnings

## Warning

```text
Unchecked cast
```

---

Most common location:

```java
return (T) this;
```

---

Example:

```java
@Override
public T getInstance() {

    return (T) this;
}
```

---

# 13. Suppress Warning Correctly

Use:

```java
@SuppressWarnings("unchecked")
```

only around:

```java
getInstance()
```

---

Example:

```java
@SuppressWarnings(
    "unchecked"
)
@Override
public T getInstance() {

    return (T) this;
}
```

---

Avoid suppressing warnings globally.

---

# 14. Fluent API Breaks

## Symptoms

This no longer works:

```java
page
    .clickEdit()
    .save()
    .validate();
```

---

Compiler says:

```text
Cannot resolve method save()
```

---

Reason:

```java
clickEdit()
```

returns:

```java
Object
```

or:

```java
CMDetailsPage
```

instead of:

```java
T
```

---

# 15. Fixing Fluent APIs

Wrong:

```java
public CMDetailsPage clickEdit()
```

---

Correct:

```java
public T clickEdit()
```

---

Then:

```java
return getInstance();
```

---

# 16. Parent Returns Wrong Type

Wrong:

```java
public CMDetailsPage save()
```

---

Correct:

```java
public T save()
```

---

Benefit:

```java
page
    .save()
    .validate()
```

continues to compile.

---

# 17. Generic Builder Not Compiling

Example:

```java
public abstract class
Builder<T> {

    public abstract T build();
}
```

---

Wrong:

```java
@Override
public Object build()
```

---

Correct:

```java
@Override
public User build()
```

---

# 18. Generic Repository Problems

Example:

```java
public interface
Repository<T> {

    T findById(
        String id
    );
}
```

---

Wrong:

```java
public Object findById(
    String id
)
```

---

Correct:

```java
public User findById(
    String id
)
```

---

# 19. Incompatible Assignment

## Error

```text
Required type:

HBDetailsPage

Provided:

CMDetailsPage
```

---

Cause:

Method returns:

```java
CMDetailsPage
```

instead of:

```java
T
```

---

Fix:

Return:

```java
T
```

everywhere.

---

# 20. Generic Collection Problems

Wrong:

```java
List documents =
    new ArrayList();
```

---

Problems:

```text
Unchecked operations
Casting errors
No autocomplete
```

---

Correct:

```java
List<Document>
```

---

# 21. Wildcard Misuse

Wrong:

```java
List<?> users
```

when updates are required.

---

Problem:

```java
users.add(...)
```

not allowed.

---

Use:

```java
List<User>
```

instead.

---

# 22. Generic Type Lost During Refactor

## Symptoms

Everything worked.

Refactor performed.

Suddenly:

```java
Method chaining broken
```

---

Diagnosis:

Search:

```java
public Object
```

---

Common culprit:

```java
clickEdit()

save()

validate()
```

---

# 23. Debugging Generic Errors

Start from:

```text
First Compilation Error
```

---

Not:

```text
Last Compilation Error
```

---

One wrong generic often triggers:

```text
50+
secondary errors
```

---

Fix first error first.

---

# 24. Practical Exercise

Fix:

```java
@Override
public Object getInstance() {

    return this;
}
```

---

Solution:

```java
@SuppressWarnings(
    "unchecked"
)
@Override
public T getInstance() {

    return (T) this;
}
```

---

# 25. Practical Exercise

Fix:

```java
public Object clickEdit()
```

---

Solution:

```java
public T clickEdit()
```

---

Return:

```java
getInstance();
```

---

# 26. Practical Exercise

Fix:

```java
public class HBDetailsPage
extends CMDetailsPage
```

---

Solution:

```java
public class HBDetailsPage
extends CMDetailsPage<
    HBDetailsPage
>
```

---

# 27. Practical Real Example

Framework:

```java
CMDetailsPage<T>
```

---

Interface:

```java
IGenericMethods<T>
```

---

Methods:

```java
clickEdit()

save()

validate()
```

---

All should return:

```java
T
```

---

Never:

```java
Object
```

---

Never:

```java
CMDetailsPage
```

unless explicitly required.

---

# 28. Recovery Procedure

When generic compilation explodes:

## Step 1

Locate:

```text
First Generic Error
```

---

## Step 2

Verify:

```java
extends
```

declaration.

---

## Step 3

Verify:

```java
implements
```

declaration.

---

## Step 4

Verify:

```java
getInstance()
```

---

## Step 5

Verify:

```java
return types
```

---

## Step 6

Rebuild:

```bash
mvn clean compile
```

---

# 29. Daily Maintenance Routine

Every week:

1. Review fluent methods.
2. Remove Object return types.
3. Review builders.
4. Review repositories.
5. Review interfaces.
6. Verify generic contracts.

---

# 30. Troubleshooting Checklist

When generic code fails:

- [ ] Verify generic bounds
- [ ] Verify child declarations
- [ ] Verify interface signatures
- [ ] Verify return types
- [ ] Verify getInstance()
- [ ] Verify fluent methods
- [ ] Verify casts
- [ ] Verify builder implementations
- [ ] Verify repository implementations
- [ ] Recompile project

---

# 31. Chapter Summary

After completing this chapter you should be able to:

- Diagnose generic compilation errors quickly
- Understand self-referencing generics
- Maintain CMDetailsPage<T> safely
- Preserve fluent APIs
- Fix bound mismatches
- Fix return type incompatibilities
- Handle cast warnings correctly
- Extend generic frameworks with confidence

This concludes:

```markdown
# Part XI - Troubleshooting
```

and prepares the foundation for:

```markdown
# Part XII - Cheatsheets
```

starting with:

```markdown
# Neovim Cheatsheet
```

which consolidates the most important commands from Chapters 1–22 into a single rapid-reference guide.

# Neovim Cheatsheet

#table-of-contents

---

# Modes

| Action | Command |
|----------|----------|
| Normal Mode | Esc |
| Insert Mode | i |
| Append | a |
| Beginning Of Line | I |
| End Of Line | A |
| New Line Below | o |
| New Line Above | O |
| Visual Mode | v |
| Visual Line | V |
| Visual Block | Ctrl-v |
| Command Mode | : |

---

# Navigation

| Action | Command |
|----------|----------|
| First Line | gg |
| Last Line | G |
| Go To Line 100 | 100G |
| Next Word | w |
| Previous Word | b |
| End Of Word | e |
| Start Of Line | 0 |
| First Character | ^ |
| End Of Line | $ |

---

# Search

| Action | Command |
|----------|----------|
| Search | /text |
| Search Backwards | ?text |
| Next Match | n |
| Previous Match | N |
| Search Current Word | * |
| Search Current Word Backwards | # |

---

# Editing

| Action | Command |
|----------|----------|
| Delete Character | x |
| Delete Word | dw |
| Delete Line | dd |
| Delete 5 Lines | 5dd |
| Copy Line | yy |
| Copy 5 Lines | 5yy |
| Paste Below | p |
| Paste Above | P |
| Undo | u |
| Redo | Ctrl-r |

---

# Text Objects

| Action | Command |
|----------|----------|
| Change Word | ciw |
| Delete Word | diw |
| Copy Word | yiw |
| Change Inside Quotes | ci" |
| Delete Inside Quotes | di" |
| Change Inside Parentheses | ci( |
| Delete Inside Parentheses | di( |
| Delete Method Body | di{ |

---

# Buffers

| Action | Command |
|----------|----------|
| List Buffers | :buffers |
| Next Buffer | :bnext |
| Previous Buffer | :bprev |
| Delete Buffer | :bd |

---

# Windows

| Action | Command |
|----------|----------|
| Horizontal Split | :split |
| Vertical Split | :vsplit |
| Move Left | Ctrl-w h |
| Move Down | Ctrl-w j |
| Move Up | Ctrl-w k |
| Move Right | Ctrl-w l |

---

# Tabs

| Action | Command |
|----------|----------|
| New Tab | :tabnew |
| Next Tab | gt |
| Previous Tab | gT |
| Close Tab | :tabclose |

---

# Telescope

| Action | Command |
|----------|----------|
| Find Files | :Telescope find_files |
| Search Text | :Telescope live_grep |
| Recent Files | :Telescope oldfiles |
| Buffers | :Telescope buffers |
| Workspace Symbols | :Telescope lsp_workspace_symbols |
| Document Symbols | :Telescope lsp_document_symbols |

---

# Java Development

| Action | Command |
|----------|----------|
| Definition | gd |
| References | gr |
| Hover | K |
| Rename | <leader>cr |
| Code Actions | <leader>ca |
| Format | :lua vim.lsp.buf.format() |

---

# Configuration

| Action | Command |
|----------|----------|
| Reload Keymaps | :lua package.loaded["config.keymaps"]=nil |
| Load Keymaps | :lua require("config.keymaps") |
| Check LSP | :LspInfo |
| Open Mason | :Mason |
| Check Health | :checkhealth |
| Plugin Manager | :Lazy |

---

# Quick Troubleshooting

```vim
:LspInfo
:checkhealth
:messages
:pwd
:Mason
:Lazy
```

---

# Maven Cheatsheet

#table-of-contents

---

# Build Lifecycle

```text
validate
compile
test
package
verify
install
deploy
```

---

# Most Used Commands

| Action | Command |
|----------|----------|
| Compile | mvn compile |
| Run Tests | mvn test |
| Clean | mvn clean |
| Clean Test | mvn clean test |
| Install | mvn clean install |

---

# Running Tests

## Single Class

```bash
mvn test -Dtest=ContentManagementTest
```

---

## Single Method

```bash
mvn test \
-Dtest=ContentManagementTest#testAddNewImportantInformationEntry
```

---

## Multiple Methods

```bash
mvn test \
-Dtest=ContentManagementTest#testOne+testTwo
```

---

# Groups

## Execute Group

```bash
mvn test -Dgroups=SMOKE
```

---

## Multiple Groups

```bash
mvn test \
-Dgroups=SMOKE,PUBLISHER
```

---

## Exclude Group

```bash
mvn test \
-DexcludedGroups=FLAKY
```

---

# XML Suites

## Execute Suite

```bash
mvn test \
-DsuiteXmlFile=suites/publisher-smoke.xml
```

---

## Multiple Suites

```bash
mvn test \
-DsuiteXmlFiles=suite1.xml,suite2.xml
```

---

# Maven Debug

## Entire Class

```bash
mvnDebug test \
-Dtest=ContentManagementTest
```

---

## Single Method

```bash
mvnDebug test \
-Dtest=ContentManagementTest#testEditAndSaveExistingImportantInformation
```

---

## XML Suite

```bash
mvnDebug test \
-DsuiteXmlFile=suites/publisher-smoke.xml
```

---

# Profiles

## Run Profile

```bash
mvn test -Ppublisher
```

---

## Active Profiles

```bash
mvn help:active-profiles
```

---

# Dependencies

## Dependency Tree

```bash
mvn dependency:tree
```

---

## Resolve Dependencies

```bash
mvn dependency:resolve
```

---

## Force Update

```bash
mvn clean install -U
```

---

# Reports

Location:

```text
target/surefire-reports
```

---

Search Failures:

```bash
grep -R "FAILED" \
target/surefire-reports
```

---

# Diagnostics

```bash
mvn compile

mvn clean test

mvn dependency:tree

mvn help:active-profiles
```

---

# Python Testing Cheatsheet

#table-of-contents

---

# Python Environment

## Create Virtual Environment

```bash
python -m venv .venv
```

---

## Activate (Linux)

```bash
source .venv/bin/activate
```

---

## Activate (Windows)

```powershell
.venv\Scripts\activate
```

---

## Install Requirements

```bash
pip install -r requirements.txt
```

---

## Generate Requirements

```bash
pip freeze > requirements.txt
```

---

# Pytest

## Run Tests

```bash
pytest
```

---

## Run Specific File

```bash
pytest test_login.py
```

---

## Run Specific Test

```bash
pytest test_login.py::test_valid_login
```

---

## Verbose

```bash
pytest -v
```

---

## Stop On First Failure

```bash
pytest -x
```

---

# Requests Library

## GET

```python
response = requests.get(url)
```

---

## POST

```python
response = requests.post(
    url,
    json=payload
)
```

---

# JSON

## Read

```python
with open(
    "payload.json",
    encoding="utf-8"
) as file:

    payload = json.load(file)
```

---

## Write

```python
with open(
    "payload.json",
    "w",
    encoding="utf-8"
) as file:

    json.dump(payload, file)
```

---

# Locust

## Launch UI

```bash
locust
```

---

## Headless

```bash
locust \
-u 100 \
-r 10 \
--headless
```

---

## CSV Reports

```bash
locust \
--csv reports/run
```

---

# Robot Framework

## Execute Tests

```bash
robot tests
```

---

## Execute By Tag

```bash
robot --include smoke
```

---

## Parallel Execution

```bash
pabot tests
```

---

# OWASP ZAP

## Baseline Scan

```bash
zap-baseline.py \
-t https://target.url
```

---

## API Scan

```bash
zap-api-scan.py
```

---

# Useful File Operations

## Read Text File

```python
with open(
    "file.txt",
    encoding="utf-8"
) as file:

    content = file.read()
```

---

## Read CSV

```python
import pandas as pd

df = pd.read_csv(
    "report.csv"
)
```

---

## Read Excel

```python
df = pd.read_excel(
    "report.xlsx"
)
```

---

# Logging

```python
import logging

logging.info("Message")
logging.error("Error")
```

---

# Debugging

```python
print(variable)
```

---

```python
breakpoint()
```

---

# Useful Commands

```bash
python --version

pip list

pip freeze

pytest

robot tests

locust

pabot tests
```

---

# Daily Workflow

```text
Activate venv
↓
Install requirements
↓
Run tests
↓
Generate reports
↓
Analyze failures
↓
Commit changes
```

---

# DAP Cheatsheet

#table-of-contents

---

# Session Control

| Action | Command |
|----------|----------|
| Start / Continue | require("dap").continue() |
| Pause | require("dap").pause() |
| Restart | require("dap").restart() |
| Terminate | require("dap").terminate() |
| Disconnect | require("dap").disconnect() |

---

# Recommended Keymaps

| Action | Key |
|----------|----------|
| Continue | F5 |
| Toggle Breakpoint | F9 |
| Step Over | F10 |
| Step Into | F11 |
| Step Out | F12 |

---

# Breakpoints

## Toggle

```lua
require("dap").toggle_breakpoint()
```

---

## Conditional Breakpoint

```lua
require("dap")
    .set_breakpoint(
        "i == 50"
    )
```

---

## Log Point

```lua
require("dap")
    .set_breakpoint(
        nil,
        nil,
        "Value={value}"
    )
```

---

# Navigation

## Step Over

```lua
require("dap").step_over()
```

---

## Step Into

```lua
require("dap").step_into()
```

---

## Step Out

```lua
require("dap").step_out()
```

---

# DAP UI

## Open

```lua
require("dapui").open()
```

---

## Close

```lua
require("dapui").close()
```

---

## Toggle

```lua
require("dapui").toggle()
```

---

# Useful Panels

```text
Variables

Scopes

Watches

Breakpoints

Call Stack
```

---

# Variables

Common debug targets:

```java
mainRecipientName

mrNameInDetails

expectedValuesHBDetails

actualValuesHBDetails
```

---

# Maven Debug

## Single Method

```bash
mvnDebug test \
-Dtest=ContentManagementTest#testEditAndSaveExistingImportantInformation
```

---

## Single Class

```bash
mvnDebug test \
-Dtest=ContentManagementTest
```

---

## XML Suite

```bash
mvnDebug test \
-DsuiteXmlFile=suites/publisher-smoke.xml
```

---

# Attach Workflow

## Start Maven

```bash
mvnDebug test
```

Expected:

```text
Listening for transport dt_socket
at address: 8000
```

---

## Check Port

```bash
netstat -ano | grep 8000
```

---

## Attach

```lua
require("dap").continue()
```

---

# Java Debug Commands

## Current Method

```vim
:JavaTestDebugCurrentMethod
```

---

## Current Class

```vim
:JavaTestDebugCurrentClass
```

---

## Current Method Run

```vim
:JavaTestRunCurrentMethod
```

---

## Current Class Run

```vim
:JavaTestRunCurrentClass
```

---

# Debugging Checklist

Before debugging:

- [ ] `mvn clean test`
- [ ] `:LspInfo`
- [ ] `:Mason`
- [ ] Breakpoint added
- [ ] Port 8000 available
- [ ] DAP UI opens

---

# Most Useful Commands

```lua
require("dap").continue()

require("dap").toggle_breakpoint()

require("dap").step_over()

require("dap").step_into()

require("dap").step_out()

require("dap").terminate()

require("dapui").open()
```

---

# TestNG Cheatsheet

#table-of-contents

---

# Core Annotations

## Test

```java
@Test
public void testLogin() {

}
```

---

## Before Method

```java
@BeforeMethod
public void setup() {

}
```

---

## After Method

```java
@AfterMethod
public void cleanup() {

}
```

---

## Before Class

```java
@BeforeClass
public void setupClass() {

}
```

---

## After Class

```java
@AfterClass
public void teardownClass() {

}
```

---

## Before Suite

```java
@BeforeSuite
public void initialize() {

}
```

---

## After Suite

```java
@AfterSuite
public void cleanupSuite() {

}
```

---

# Execution Order

```text
@BeforeSuite

@BeforeClass

@BeforeMethod

@Test

@AfterMethod

@AfterClass

@AfterSuite
```

---

# Groups

## Declare

```java
@Test(
    groups = {
        SMOKE,
        PUBLISHER
    }
)
```

---

## Run

```bash
mvn test \
-Dgroups=SMOKE
```

---

## Multiple Groups

```bash
mvn test \
-Dgroups=SMOKE,PUBLISHER
```

---

## Exclude

```bash
mvn test \
-DexcludedGroups=FLAKY
```

---

# Most Common Groups

```java
SMOKE

REGRESSION

SANITY

CONTENT_MANAGEMENT

DOCUMENT_MANAGEMENT

CREATOR

PUBLISHER

VALIDATOR

EVERYDAY_RUN
```

---

# Dependencies

## Depends On Method

```java
@Test
public void createUser() {

}
```

```java
@Test(
    dependsOnMethods =
        "createUser"
)
public void editUser() {

}
```

---

# Priority

```java
@Test(priority = 1)
```

---

```java
@Test(priority = 2)
```

---

Prefer:

```java
dependsOnMethods
```

over:

```java
priority
```

when possible.

---

# Data Provider

## Create

```java
@DataProvider
public Object[][] users() {

    return new Object[][]{
        {"user1"},
        {"user2"}
    };
}
```

---

## Use

```java
@Test(
    dataProvider = "users"
)
public void testUser(
        String username) {

}
```

---

# Retry Analyzer

## Usage

```java
@Test(
    retryAnalyzer =
        RetryAnalyzer.class
)
```

---

## Implementation

```java
public class RetryAnalyzer
implements IRetryAnalyzer {

}
```

---

# Listeners

## Registration

```java
@Listeners(
    TestListener.class
)
```

---

## Common Events

```java
onTestFailure()

onTestSuccess()

onTestSkipped()

onStart()

onFinish()
```

---

# Screenshot On Failure

```java
@Override
public void onTestFailure(
        ITestResult result) {

    Screenshots
        .takeScreenShotAsFile();
}
```

---

# Execute Tests

## Entire Project

```bash
mvn test
```

---

## Single Class

```bash
mvn test \
-Dtest=ContentManagementTest
```

---

## Single Method

```bash
mvn test \
-Dtest=ContentManagementTest#testAddNewImportantInformationEntry
```

---

# XML Suites

## Execute Suite

```bash
mvn test \
-DsuiteXmlFile=suites/publisher-smoke.xml
```

---

## Example

```xml
<suite>

    <test>

        <classes>

            <class
                name="tests.ContentManagementTest"/>

        </classes>

    </test>

</suite>
```

---

# Parallel Execution

## Methods

```xml
parallel="methods"
```

---

## Classes

```xml
parallel="classes"
```

---

## Tests

```xml
parallel="tests"
```

---

## Thread Count

```xml
thread-count="4"
```

---

# Common Assertions

## Equals

```java
assertEquals(
    actual,
    expected
);
```

---

## True

```java
assertTrue(
    condition
);
```

---

## False

```java
assertFalse(
    condition
);
```

---

## Not Null

```java
assertNotNull(
    object
);
```

---

# Troubleshooting

## Tests Not Found

Verify:

```java
@Test
```

annotation exists.

---

## XML Not Executing

Verify:

```xml
<class name="..." />
```

path.

---

## Groups Missing

Verify:

```java
groups = {}
```

matches:

```bash
-Dgroups=
```

---

## Retry Not Triggering

Verify:

```java
retryAnalyzer =
```

configured.

---

# Daily Commands

```bash
mvn test

mvn clean test

mvn test -Dgroups=SMOKE

mvn test -Dtest=ClassName

mvnDebug test
```

---

# TestNG Architecture Reminder

```text
BaseTest
    ↓
Feature Test
    ↓
Page Objects
    ↓
Assertions
```

---

# Daily Checklist

- [ ] Tests compile
- [ ] Groups configured
- [ ] XML suites valid
- [ ] Retry configured
- [ ] Screenshots enabled
- [ ] Reports generated
- [ ] Single method execution works
- [ ] Maven debug works

---

# Selenide Cheatsheet

#table-of-contents

---

# Core Classes

```java
SelenideElement

ElementsCollection

Condition

Configuration
```

---

# Element Selectors

## By ID

```java
$("#save")
```

Equivalent:

```java
$(By.id("save"))
```

---

## By CSS

```java
$(".button")
```

---

```java
$("div.content")
```

---

## By XPath

```java
$x("//button")
```

---

## By Text

```java
$(byText("Save"))
```

---

## Partial Text

```java
$(withText("Save"))
```

---

# SelenideElement

## Click

```java
BUTTON.click();
```

---

## Set Value

```java
USERNAME.setValue(
    "admin"
);
```

---

## Clear

```java
USERNAME.clear();
```

---

## Append

```java
USERNAME.append(
    "_new"
);
```

---

## Get Text

```java
String value =
    LABEL.getText();
```

---

## Get Attribute

```java
String value =
    ELEMENT.getAttribute(
        "value"
    );
```

---

# Conditions

## Visible

```java
element.shouldBe(
    Condition.visible
);
```

---

## Hidden

```java
element.shouldBe(
    Condition.hidden
);
```

---

## Exist

```java
element.should(
    Condition.exist
);
```

---

## Enabled

```java
element.shouldBe(
    Condition.enabled
);
```

---

## Disabled

```java
element.shouldBe(
    Condition.disabled
);
```

---

# Text Assertions

## Exact Text

```java
element.shouldHave(
    Condition.exactText(
        "Saved"
    )
);
```

---

## Partial Text

```java
element.shouldHave(
    Condition.text(
        "Saved"
    )
);
```

---

## Case Sensitive

```java
element.shouldHave(
    Condition.exactText(
        value
    )
);
```

---

# Value Assertions

```java
INPUT.shouldHave(
    Condition.value(
        "admin"
    )
);
```

---

# Waiting

## Wait For Visible

```java
element.shouldBe(
    Condition.visible
);
```

---

## Wait For Hidden

```java
element.shouldBe(
    Condition.hidden
);
```

---

## Wait For Text

```java
MESSAGE.shouldHave(
    Condition.text(
        "Success"
    )
);
```

---

# Never Use

❌

```java
Thread.sleep(5000);
```

---

✅

```java
BUTTON.shouldBe(
    Condition.visible
);
```

---

# ElementsCollection

## Create Collection

```java
ElementsCollection rows =
    $$("tr");
```

---

## Size

```java
rows.size();
```

---

## First

```java
rows.first();
```

---

## Last

```java
rows.last();
```

---

## By Index

```java
rows.get(0);
```

---

# Collection Search

## Find By Text

```java
rows.findBy(
    Condition.text(
        "John Smith"
    )
);
```

---

## Filter Visible

```java
rows.filterBy(
    Condition.visible
);
```

---

## Get All Texts

```java
rows.texts();
```

---

# Tables

## All Rows

```java
ElementsCollection rows =
    $$("tbody tr");
```

---

## Find Specific Row

```java
rows.findBy(
    Condition.text(
        expectedName
    )
);
```

---

## Avoid

❌

```java
rows.get(0)
```

---

Prefer:

✅

```java
rows.findBy(
    Condition.text(
        expectedName
    )
);
```

---

# Scrolling

## Scroll Into View

```java
element.scrollIntoView(
    true
);
```

---

## Click After Scroll

```java
element
    .scrollIntoView(true)
    .click();
```

---

# Page Validation

## Page Loaded

```java
PAGE_TITLE.shouldBe(
    Condition.visible
);
```

---

## URL Validation

```java
webdriver()
    .driver()
    .url();
```

---

# File Upload

```java
INPUT.uploadFile(
    new File(
        "document.pdf"
    )
);
```

---

# File Download

```java
File file =
    DOWNLOAD_BUTTON.download();
```

---

# Browser Configuration

## Browser

```java
Configuration.browser =
    "chrome";
```

---

## Timeout

```java
Configuration.timeout =
    15000;
```

---

## Headless

```java
Configuration.headless =
    true;
```

---

## Keep Browser Open

```java
Configuration.holdBrowserOpen =
    true;
```

---

## Save Page Source

```java
Configuration.savePageSource =
    true;
```

---

# Screenshots

## Manual Screenshot

```java
Screenshots
    .takeScreenShotAsFile();
```

---

## Screenshot Path

Usually:

```text
build/reports/tests
```

or

```text
target/screenshots
```

depending on framework.

---

# Common Assertions

## Equals

```java
assertEquals(
    actual,
    expected
);
```

---

## Not Null

```java
assertNotNull(
    value
);
```

---

## Selenide Style

```java
LABEL.shouldHave(
    Condition.text(
        expectedText
    )
);
```

---

# Page Object Example

```java
public class LoginPage {

    public HomePage login(
            String user,
            String pass) {

        USERNAME.setValue(
            user
        );

        PASSWORD.setValue(
            pass
        );

        BTN_LOGIN.click();

        return new HomePage();
    }
}
```

---

# Fluent API Example

```java
contentManagementPage
    .clickEdit()
    .save()
    .validate();
```

---

# Troubleshooting

## Element Not Found

```java
element.shouldBe(
    Condition.visible
);
```

---

## Element Not Visible

```java
element.scrollIntoView(
    true
);
```

---

## Stale Element

Re-locate:

```java
$("...")
```

---

## Empty Collection

Debug:

```java
rows.size()
```

---

## Download Fails

Verify:

```java
Configuration.fileDownload
```

---

## Timeout

Verify:

```java
Configuration.timeout
```

---

## Flaky Tests

Remove:

```java
Thread.sleep()
```

Use:

```java
Condition.visible
```

---

# Common Locators

## ID

```java
$("#id")
```

---

## CSS

```java
$(".class")
```

---

## XPath

```java
$x("//button")
```

---

## Data Test Id

```java
$("[data-testid='save']")
```

Recommended.

---

# Debugging

## Current Text

```java
element.getText();
```

---

## Collection Size

```java
rows.size();
```

---

## First Row

```java
rows.first().getText();
```

---

## DAP Variables

Useful targets:

```java
rows

mainRecipientName

expectedValuesHBDetails

actualValuesHBDetails
```

---

# Daily Workflow

```text
Open Page
↓
Wait For Visible
↓
Interact
↓
Validate Result
↓
Capture Screenshot On Failure
↓
Debug Collections If Needed
```

---

# Anti-Patterns

❌

```java
Thread.sleep()
```

❌

```java
/html/body/div[1]/...
```

❌

```java
rows.get(0)
```

❌

```java
click()
without validation
```

---

# Best Practices

✅

```java
Condition.visible
```

✅

```java
ElementsCollection
```

✅

```java
findBy()
```

✅

```java
Page Objects
```

✅

```java
Fluent APIs
```

✅

```java
Stable data-testid locators
```

---

# Robot Framework Cheatsheet

#table-of-contents

---

# File Structure

```text
robotframework
│
├── tests
│
├── resources
│
├── variables
│
├── libraries
│
├── data
│
└── reports
```

---

# Standard Robot File

```robot
*** Settings ***

*** Variables ***

*** Test Cases ***

*** Keywords ***
```

---

# Settings Section

## Import Library

```robot
*** Settings ***

Library
    Browser
```

---

## Import Resource

```robot
*** Settings ***

Resource
    ../resources/common.robot
```

---

## Import Variables

```robot
*** Settings ***

Variables
    ../variables/environment.py
```

---

# Variables

## String

```robot
${USERNAME}
```

---

## Integer

```robot
${TIMEOUT}
```

---

## List

```robot
@{USERS}
```

---

## Dictionary

```robot
&{CONFIG}
```

---

# Test Case

```robot
*** Test Cases ***

User Can Login

    Open Browser

    Login

    Verify Dashboard
```

---

# Documentation

```robot
*** Test Cases ***

User Can Login

    [Documentation]
    Verify publisher login
```

---

# Tags

```robot
*** Test Cases ***

User Can Login

    [Tags]
    smoke
    publisher
```

---

# Execute By Tag

## Include

```bash
robot --include smoke
```

---

## Multiple Tags

```bash
robot \
--include smoke \
--include publisher
```

---

## Exclude

```bash
robot --exclude regression
```

---

# Variables Usage

## Example

```robot
Input Text

    ${USERNAME}
```

---

## Access Variable

```robot
${BASE_URL}
```

---

# Keywords

## Definition

```robot
*** Keywords ***

Login

    Input Text

    Click
```

---

## Usage

```robot
*** Test Cases ***

User Can Login

    Login
```

---

# Arguments

## Keyword With Arguments

```robot
*** Keywords ***

Login

    [Arguments]

    ${username}

    ${password}

    Input Text
```

---

## Usage

```robot
Login

    admin

    secret
```

---

# Browser Library

## New Browser

```robot
New Browser

    chromium
```

---

## New Context

```robot
New Context
```

---

## New Page

```robot
New Page
```

---

## Go To

```robot
Go To

    ${URL}
```

---

# Input Operations

## Fill Text

```robot
Fill Text

    id=username

    admin
```

---

## Type Text

```robot
Type Text

    id=password

    secret
```

---

# Click Operations

## Click

```robot
Click

    text=Save
```

---

## Double Click

```robot
Double Click

    text=Save
```

---

# Assertions

## Text Should Be

```robot
Get Text

    id=result
```

---

```robot
Should Be Equal

    ${actual}

    ${expected}
```

---

## Contains

```robot
Should Contain

    ${actual}

    Success
```

---

## Element Visible

```robot
Get Element States

    text=Save
```

---

# Waiting

## Wait For Element

```robot
Wait For Elements State

    text=Save

    visible
```

---

## Wait For Page

```robot
Wait For Elements State

    h1

    visible
```

---

# RequestsLibrary

## Import

```robot
Library
    RequestsLibrary
```

---

## Create Session

```robot
Create Session

    api

    ${BASE_URL}
```

---

## GET Request

```robot
GET On Session

    api

    /documents
```

---

## POST Request

```robot
POST On Session

    api

    /documents
```

---

# JSON Validation

```robot
Should Be Equal

    ${response.status_code}

    200
```

---

# Loops

## FOR

```robot
FOR

    ${user}

    IN

    @{USERS}

    Log

    ${user}

END
```

---

# IF Statements

```robot
IF

    ${status} == 200

    Log

    Success

END
```

---

# Python Libraries

## Import

```robot
Library
    AuthenticationLibrary.py
```

---

## Call Method

Python:

```python
def login():
    pass
```

---

Robot:

```robot
Login
```

---

# Resources

## Resource Structure

```text
resources
│
├── common.robot
├── login.robot
├── navigation.robot
└── content_management.robot
```

---

# Recommended Keywords

## Authentication

```robot
Login As Creator

Login As Publisher

Login As Validator

Login As Admin
```

---

## Navigation

```robot
Open Content Management

Open Operations

Open Events

Open Analysis
```

---

# Recommended Tags

```text
smoke

regression

publisher

creator

validator

content_management

analysis

operations

events
```

---

# Reports

Generated automatically:

```text
report.html

log.html

output.xml
```

---

# Open Report

Linux:

```bash
xdg-open report.html
```

---

Windows:

```bash
start report.html
```

---

# Parallel Execution

## Install

```bash
pip install robotframework-pabot
```

---

## Execute

```bash
pabot tests
```

---

## 4 Processes

```bash
pabot \
--processes 4 \
tests
```

---

# Browser Debugging

## Slow Motion

```robot
New Browser

    chromium

    slowMo=1000
```

---

Useful when debugging UI flows.

---

# Logging

## Log Message

```robot
Log

    Current User
```

---

## Log Variable

```robot
Log

    ${USERNAME}
```

---

# Screenshot

```robot
Take Screenshot
```

---

# Execute Tests

## All Tests

```bash
robot tests
```

---

## Single File

```bash
robot tests/login.robot
```

---

## Specific Folder

```bash
robot tests/publisher
```

---

# Integration With Your Ecosystem

## Shared Payloads

```text
locustPerformanceTesting
│
└── payloads
```

Reuse from:

```text
Robot Framework

Locust

Security Tests
```

---

# Eurosur Structure

```text
tests
│
├── eurosur10
│
│   ├── events
│   ├── operations
│   └── analysis
│
└── eurosur15
    ├── events
    ├── operations
    └── analysis
```

---

# Troubleshooting

## Library Not Found

```bash
pip list
```

---

## Browser Doesn't Start

```bash
rfbrowser init
```

---

## Variable Missing

Verify:

```robot
${VARIABLE}
```

exists.

---

## Tag Not Executed

Verify:

```robot
[Tags]
```

---

## API Fails

Verify:

```robot
Create Session
```

executed.

---

# Most Useful Commands

```bash
robot tests

robot --include smoke

robot --exclude regression

pabot tests

rfbrowser init
```

---

# Daily Workflow

```text
Execute Tests
↓
Review Reports
↓
Investigate Failures
↓
Update Keywords
↓
Refactor Resources
↓
Commit Changes
```

---

# Best Practices

✅

```robot
Reusable Keywords
```

✅

```robot
Resources Folder
```

✅

```robot
Tags
```

✅

```robot
Browser Library
```

✅

```robot
RequestsLibrary
```

✅

```robot
Custom Python Libraries
```

---

# Anti-Patterns

❌

```robot
Huge Test Cases
```

❌

```robot
Duplicated Steps
```

❌

```robot
Hardcoded URLs
```

❌

```robot
Hardcoded Credentials
```

❌

```robot
No Tags
```

---
````**

# Locust Cheatsheet

#table-of-contents

---

# Installation

## Install Locust

```bash
pip install locust
```

---

## Verify Installation

```bash
locust --version
```

---

# Recommended Project Structure

```text
locustPerformanceTesting
│
├── locustfile.py
│
├── users
│
├── tasks
│
├── payloads
│
├── reports
│
└── utils
```

---

# Core Classes

```python
HttpUser

TaskSet

SequentialTaskSet

FastHttpUser
```

---

# Basic User

```python
from locust import HttpUser

class PublisherUser(HttpUser):
    pass
```

---

# Basic Task

```python
from locust import task

@task
def homepage(self):

    self.client.get("/")
```

---

# Complete Example

```python
from locust import (
    HttpUser,
    task,
    between
)

class PublisherUser(HttpUser):

    wait_time = between(1, 5)

    @task
    def documents(self):

        self.client.get(
            "/documents"
        )
```

---

# Wait Times

## Fixed

```python
wait_time =
    between(1, 1)
```

---

## Random

```python
wait_time =
    between(1, 5)
```

---

## Realistic User

```python
wait_time =
    between(2, 10)
```

---

# Tasks

## Single Task

```python
@task
def login(self):
    pass
```

---

## Multiple Tasks

```python
@task
def search(self):
    pass

@task
def logout(self):
    pass
```

---

# Task Weights

## Higher Frequency

```python
@task(5)
def search(self):
    pass
```

---

## Lower Frequency

```python
@task(1)
def delete(self):
    pass
```

---

Meaning:

```text
search
5x more frequently
than delete
```

---

# Requests

## GET

```python
self.client.get(
    "/documents"
)
```

---

## POST

```python
self.client.post(
    "/documents",
    json=payload
)
```

---

## PUT

```python
self.client.put(
    "/documents/1",
    json=payload
)
```

---

## DELETE

```python
self.client.delete(
    "/documents/1"
)
```

---

# Authentication

## Login Request

```python
response =
    self.client.post(
        "/login",
        json=credentials
    )
```

---

## Store Token

```python
token =
    response.json()["token"]
```

---

## Use Token

```python
headers = {
    "Authorization":
    f"Bearer {token}"
}
```

---

# Session Lifecycle

## Before Execution

```python
def on_start(self):

    self.login()
```

---

## After Execution

```python
def on_stop(self):

    self.logout()
```

---

# Payload Reuse

## Read JSON

```python
import json

with open(
        "payloads/document.json"
) as file:

    payload =
        json.load(file)
```

---

## Send Payload

```python
self.client.post(
    "/documents",
    json=payload
)
```

---

# User Types

Example matching your application roles:

```python
PublisherUser

CreatorUser

ValidatorUser

AdminUser
```

---

# Running Locust

## Start UI

```bash
locust
```

---

## Open Dashboard

```text
http://localhost:8089
```

---

# Headless Mode

## Basic

```bash
locust --headless
```

---

## Example

```bash
locust \
-u 100 \
-r 10 \
--headless
```

---

Meaning:

```text
100 users

10 users/second
```

---

# Runtime

## 10 Minutes

```bash
locust \
-u 100 \
-r 10 \
--run-time 10m \
--headless
```

---

## 1 Hour

```bash
locust \
-u 500 \
-r 25 \
--run-time 1h \
--headless
```

---

# Ramp-Up

## Example

```bash
locust \
-u 500 \
-r 25
```

---

Meaning:

```text
25 new users every second

until 500 users reached
```

---

# CSV Reports

## Generate

```bash
locust \
-u 100 \
-r 10 \
--csv reports/run \
--headless
```

---

# Generated Files

```text
run_stats.csv

run_failures.csv

run_history.csv
```

---

# Most Important Metrics

## Average

```text
Average Response Time
```

---

## Throughput

```text
Requests/Second
```

---

## Error Rate

```text
Failed Requests %
```

---

## Percentiles

```text
P50

P90

P95

P99
```

---

# Percentiles

## P50

```text
50% requests faster
than this value
```

---

## P95

```text
95% requests faster
than this value
```

---

## P99

```text
99% requests faster
than this value
```

---

# Example Analysis

Good:

```text
P95 = 500ms

Errors = 0.2%
```

---

Bad:

```text
P95 = 7000ms

Errors = 5%
```

---

# Common Thresholds

Example SLA:

```text
P95 < 2s

Error Rate < 1%

Availability > 99%
```

---

# CSV Analysis

## Pandas

```python
import pandas as pd

df =
    pd.read_csv(
        "run_stats.csv"
    )
```

---

## Excel

```text
Open CSV
Review:

Response Times

Failures

Percentiles
```

---

# FastHttpUser

Alternative:

```python
from locust import
FastHttpUser
```

---

Benefits:

```text
Lower CPU Usage

More Users Per Machine
```

---

# Sequential Tasks

## Ordered Execution

```python
from locust import
SequentialTaskSet
```

---

Example:

```python
Login
→
Search
→
Open
→
Logout
```

---

# Tags

## Define

```python
from locust import tag

@tag("smoke")
@task
def search(self):
    pass
```

---

## Execute Tag

```bash
locust \
--tags smoke
```

---

# Logging

```python
import logging

logging.info(
    "Search executed"
)
```

---

## Error

```python
logging.error(
    "Request failed"
)
```

---

# Common User Simulation

```text
50 Publishers

25 Creators

25 Validators
```

---

Actions:

```text
Login

Search

Open Document

Logout
```

---

# CI/CD

## Headless Execution

```bash
locust \
--headless \
-u 100 \
-r 10 \
--run-time 10m
```

---

# Pipeline Outputs

```text
CSV Reports

HTML Reports

Performance Trends
```

---

# Useful Commands

## Start UI

```bash
locust
```

---

## Headless

```bash
locust --headless
```

---

## CSV

```bash
locust --csv reports/run
```

---

## Tagged Tests

```bash
locust --tags smoke
```

---

# Troubleshooting

## Too Many Failures

Check:

```text
Authentication

Tokens

Permissions

Rate Limits
```

---

## Empty Results

Verify:

```text
Correct Base URL
```

---

## High Response Times

Investigate:

```text
Backend

Database

Network
```

---

## User Collisions

Avoid:

```text
Single Shared User
```

---

Use:

```text
User Pool
```

---

# Best Practices

✅

```python
Reusable Payloads
```

✅

```python
User Pools
```

✅

```python
P95 Monitoring
```

✅

```python
CI/CD Integration
```

✅

```python
Separate Users By Role
```

---

# Anti-Patterns

❌

```python
Hardcoded Credentials
```

❌

```python
One Shared User
```

❌

```python
Ignoring P95
```

❌

```python
Using Average Only
```

❌

```python
No Ramp-Up Strategy
```

---

# Daily Workflow

```text
Prepare Payloads
↓
Authenticate Users
↓
Execute Locust
↓
Generate CSV Reports
↓
Review P95
↓
Review Errors
↓
Review Throughput
↓
Commit Improvements
```

---

# Locust CSV Automatic Analysis

#table-of-contents

---

# 1. Objective

After every Locust execution:

```bash
locust \
--headless \
-u 100 \
-r 10 \
--run-time 10m \
--csv reports/run
```

generate automatically:

```text
Performance Summary
P50
P90
P95
P99
Error Rate
Throughput
Slowest Endpoints
Failed Endpoints
PASS / FAIL
```

without manually opening Excel.

---

# 2. Generated Files

Locust creates:

```text
run_stats.csv
run_failures.csv
run_history.csv
```

---

# 3. Recommended Structure

```text
locustPerformanceTesting
│
├── reports
│
│   ├── run_stats.csv
│   ├── run_failures.csv
│   ├── run_history.csv
│   │
│   └── analysis
│       ├── summary.html
│       ├── summary.md
│       └── summary.json
│
└── tools
    └── analyze_results.py
```

---

# 4. Install Dependencies

```bash
pip install pandas
```

---

# 5. Read CSV File

```python
import pandas as pd

stats = pd.read_csv(
    "reports/run_stats.csv"
)
```

---

# 6. Most Important Columns

Typical columns:

```text
Name

Request Count

Failure Count

Median Response Time

Average Response Time

Min Response Time

Max Response Time

Average Content Size

Requests/s
```

---

# 7. Basic Summary

```python
import pandas as pd

stats = pd.read_csv(
    "reports/run_stats.csv"
)

print(stats.describe())
```

---

# 8. Global Throughput

```python
total_rps = stats[
    "Requests/s"
].sum()

print(total_rps)
```

---

# 9. Error Rate

```python
total_requests =
    stats["Request Count"].sum()

total_failures =
    stats["Failure Count"].sum()

error_rate = (
    total_failures
    / total_requests
) * 100
```

---

# 10. P95 Validation

Define SLA:

```text
P95 < 2000 ms
```

---

Validation:

```python
if p95 < 2000:
    print("PASS")
else:
    print("FAIL")
```

---

# 11. Throughput Validation

Example SLA:

```text
Requests/s > 50
```

---

Check:

```python
if total_rps > 50:
    print("PASS")
```

---

# 12. Failed Requests

```python
failures = pd.read_csv(
    "reports/run_failures.csv"
)

print(failures)
```

---

# 13. Top Slow Endpoints

```python
slowest =
    stats.sort_values(
        by="Average Response Time",
        ascending=False
    )

print(slowest.head(10))
```

---

# 14. Top Failing Endpoints

```python
worst =
    stats.sort_values(
        by="Failure Count",
        ascending=False
    )

print(worst.head(10))
```

---

# 15. HTML Report

```python
html =
    stats.to_html()

with open(
    "summary.html",
    "w",
    encoding="utf-8"
) as file:

    file.write(html)
```

---

# 16. Markdown Report

```python
report = f"""
# Performance Report

Requests:
{total_requests}

Errors:
{total_failures}

Error Rate:
{error_rate:.2f}%
"""
```

---

Save:

```python
summary.md
```

---

# 17. JSON Report

```python
import json

summary = {

    "requests":
        total_requests,

    "failures":
        total_failures,

    "error_rate":
        error_rate,

    "rps":
        total_rps
}
```

---

Save:

```python
summary.json
```

---

# 18. SLA Validation

Recommended:

```python
P95 < 2000 ms

P99 < 5000 ms

Error Rate < 1%

Requests/s > 50
```

---

# 19. Automatic PASS / FAIL

```python
status = "PASS"

if p95 > 2000:
    status = "FAIL"

if error_rate > 1:
    status = "FAIL"
```

---

# 20. Terminal Output

Example:

```text
--------------------------------

Performance Report

Requests:      15643
Failures:      16
Error Rate:    0.10%

P95:           842 ms
P99:           1430 ms

Throughput:    122 req/s

Result: PASS

--------------------------------
```

---

# 21. Integration With CI/CD

GitHub:

```yaml
- name: Run Locust
  run: |
    locust \
    --headless \
    --csv reports/run
```

---

Run analysis:

```yaml
- name: Analyze
  run: |
    python analyze_results.py
```

---

# 22. Azure DevOps

```yaml
- script: |
    python analyze_results.py
```

---

Fail pipeline:

```python
if status == "FAIL":
    exit(1)
```

---

# 23. Trend Analysis

Store:

```text
run1.json
run2.json
run3.json
```

---

Compare:

```text
P95

P99

Error Rate

Requests/s
```

between releases.

---

# 24. Recommended Enterprise Thresholds

Example:

```text
P95 < 2s

P99 < 5s

Error Rate < 1%

Availability > 99%

Requests/s > 50
```

---

# 25. Reusable Analysis Script

Recommended file:

```text
tools/analyze_results.py
```

Executed after every:

```bash
locust --headless
```

---

# 26. Daily Workflow

```text
Run Locust
↓
Generate CSV
↓
Run Analysis Script
↓
Generate Markdown Report
↓
Generate JSON Report
↓
Validate SLA
↓
PASS / FAIL
```

---

# Best Practice

For your environment:

```text
Locust
↓
CSV Reports
↓
Pandas Analysis
↓
JSON Summary
↓
Azure DevOps
↓
Automatic Quality Gate
```

from pathlib import Path
import json
import sys
from typing import Optional

import pandas as pd


# ============================================================================
# CONFIGURATION
# ============================================================================

REPORT_DIR = Path("reports")

STATS_FILE = REPORT_DIR / "run_stats.csv"
FAILURES_FILE = REPORT_DIR / "run_failures.csv"
HISTORY_FILE = REPORT_DIR / "run_history.csv"

OUTPUT_JSON = REPORT_DIR / "summary.json"
OUTPUT_MD = REPORT_DIR / "summary.md"
OUTPUT_HTML = REPORT_DIR / "summary.html"


SLA = {
    "p95_ms": 2000,
    "p99_ms": 5000,
    "error_rate_percent": 1.0,
    "throughput_rps": 50
}


# ============================================================================
# HELPERS
# ============================================================================

def find_column(
    df: pd.DataFrame,
    options: list[str]
) -> str:
    """
    Finds the first matching column.
    """

    columns = {
        c.lower(): c
        for c in df.columns
    }

    for option in options:

        for lower_name, original_name in columns.items():

            if option.lower() in lower_name:
                return original_name

    raise ValueError(
        f"Could not find any of these columns: {options}"
    )


def safe_sum(
    df: pd.DataFrame,
    column: str
) -> float:

    if column not in df.columns:
        return 0

    return (
        pd.to_numeric(
            df[column],
            errors="coerce"
        )
        .fillna(0)
        .sum()
    )


def safe_mean(
    df: pd.DataFrame,
    column: str
) -> float:

    if column not in df.columns:
        return 0

    return (
        pd.to_numeric(
            df[column],
            errors="coerce"
        )
        .fillna(0)
        .mean()
    )


def detect_percentile_column(
    df: pd.DataFrame,
    percentile: str
) -> Optionalfor column in df.columns:

        if percentile in column.lower():
            return column

    return None


# ============================================================================
# LOAD DATA
# ============================================================================

if not STATS_FILE.exists():

    print(
        f"ERROR: {STATS_FILE} not found"
    )

    sys.exit(1)

stats = pd.read_csv(STATS_FILE)

if FAILURES_FILE.exists():

    failures = pd.read_csv(
        FAILURES_FILE
    )

else:

    failures = pd.DataFrame()

if HISTORY_FILE.exists():

    history = pd.read_csv(
        HISTORY_FILE
    )

else:

    history = pd.DataFrame()


# ============================================================================
# DETECT COLUMN NAMES
# ============================================================================

request_count_col = find_column(
    stats,
    [
        "request count",
        "# requests"
    ]
)

failure_count_col = find_column(
    stats,
    [
        "failure count",
        "# failures"
    ]
)

avg_response_col = find_column(
    stats,
    [
        "average response",
        "avg response"
    ]
)

rps_col = find_column(
    stats,
    [
        "requests/s",
        "requests per second"
    ]
)

name_col = find_column(
    stats,
    [
        "name"
    ]
)

p95_col = detect_percentile_column(
    stats,
    "95"
)

p99_col = detect_percentile_column(
    stats,
    "99"
)


# ============================================================================
# GLOBAL METRICS
# ============================================================================

total_requests = safe_sum(
    stats,
    request_count_col
)

total_failures = safe_sum(
    stats,
    failure_count_col
)

total_rps = safe_sum(
    stats,
    rps_col
)

avg_response = safe_mean(
    stats,
    avg_response_col
)

error_rate = (
    (
        total_failures
        / total_requests
    ) * 100
    if total_requests > 0
    else 0
)


# ============================================================================
# P95 / P99
# ============================================================================

if p95_col:

    p95 = (
        pd.to_numeric(
            stats[p95_col],
            errors="coerce"
        )
        .fillna(0)
        .max()
    )

else:

    p95 = avg_response

if p99_col:

    p99 = (
        pd.to_numeric(
            stats[p99_col],
            errors="coerce"
        )
        .fillna(0)
        .max()
    )

else:

    p99 = avg_response


# ============================================================================
# SLA VALIDATION
# ============================================================================

violations = []

if p95 > SLA["p95_ms"]:

    violations.append(
        (
            f"P95 ({p95:.0f}ms) "
            f"> SLA ({SLA['p95_ms']}ms)"
        )
    )

if p99 > SLA["p99_ms"]:

    violations.append(
        (
            f"P99 ({p99:.0f}ms) "
            f"> SLA ({SLA['p99_ms']}ms)"
        )
    )

if error_rate > SLA["error_rate_percent"]:

    violations.append(
        (
            f"Error Rate "
            f"({error_rate:.2f}%) "
            f"> SLA "
            f"({SLA['error_rate_percent']}%)"
        )
    )

if total_rps < SLA["throughput_rps"]:

    violations.append(
        (
            f"Throughput "
            f"({total_rps:.2f} req/s) "
            f"< SLA "
            f"({SLA['throughput_rps']} req/s)"
        )
    )


status = "PASS"

if violations:
    status = "FAIL"


print("=" * 80)
print("LOCUST PERFORMANCE ANALYZER")
print("=" * 80)

print(f"Requests      : {int(total_requests)}")
print(f"Failures      : {int(total_failures)}")
print(f"Error Rate    : {error_rate:.2f}%")
print(f"Throughput    : {total_rps:.2f} req/s")
print(f"Average       : {avg_response:.2f} ms")
print(f"P95           : {p95:.2f} ms")
print(f"P99           : {p99:.2f} ms")
print(f"Status        : {status}")

print("=" * 80)


# ============================================================================
# PART 2 CONTINUES HERE
# ============================================================================

# ============================================================================
# TOP SLOW ENDPOINTS
# ============================================================================

slowest = stats.sort_values(
    by=avg_response_col,
    ascending=False
).head(10)

slowest_rows = []

for _, row in slowest.iterrows():

    slowest_rows.append(
        {
            "endpoint": str(
                row[name_col]
            ),

            "avg_ms": float(
                pd.to_numeric(
                    row[avg_response_col],
                    errors="coerce"
                )
            )
        }
    )

print()
print("TOP SLOW ENDPOINTS")
print("-" * 80)

for endpoint in slowest_rows:

    print(
        f"{endpoint['endpoint']} : "
        f"{endpoint['avg_ms']:.2f} ms"
    )

print("-" * 80)


# ============================================================================
# TOP FAILING ENDPOINTS
# ============================================================================

worst = stats.sort_values(
    by=failure_count_col,
    ascending=False
).head(10)

worst_rows = []

for _, row in worst.iterrows():

    failures_count = float(
        pd.to_numeric(
            row[failure_count_col],
            errors="coerce"
        )
    )

    if failures_count > 0:

        worst_rows.append(
            {
                "endpoint": str(
                    row[name_col]
                ),

                "failures":
                    failures_count
            }
        )

print()
print("TOP FAILING ENDPOINTS")
print("-" * 80)

if worst_rows:

    for endpoint in worst_rows:

        print(
            f"{endpoint['endpoint']} : "
            f"{endpoint['failures']:.0f} failures"
        )

else:

    print("No failing endpoints.")

print("-" * 80)


# ============================================================================
# CHART DATA
# ============================================================================

slow_labels = [
    item["endpoint"]
    for item in slowest_rows
]

slow_values = [
    item["avg_ms"]
    for item in slowest_rows
]

failure_labels = [
    item["endpoint"]
    for item in worst_rows
]

failure_values = [
    item["failures"]
    for item in worst_rows
]


# ============================================================================
# HISTORY DATA
# ============================================================================

history_timestamps = []
history_rps = []
history_failures = []
history_response_time = []

if not history.empty:

    try:

        timestamp_col = find_column(
            history,
            [
                "timestamp"
            ]
        )

        history_timestamps = (
            history[timestamp_col]
            .astype(str)
            .tolist()
        )

    except Exception:
        pass

    try:

        rps_history_col = find_column(
            history,
            [
                "requests/s"
            ]
        )

        history_rps = (
            pd.to_numeric(
                history[rps_history_col],
                errors="coerce"
            )
            .fillna(0)
            .tolist()
        )

    except Exception:
        pass

    try:

        failures_history_col = find_column(
            history,
            [
                "failures/s"
            ]
        )

        history_failures = (
            pd.to_numeric(
                history[
                    failures_history_col
                ],
                errors="coerce"
            )
            .fillna(0)
            .tolist()
        )

    except Exception:
        pass

    try:

        response_history_col = find_column(
            history,
            [
                "average response",
                "avg response"
            ]
        )

        history_response_time = (
            pd.to_numeric(
                history[
                    response_history_col
                ],
                errors="coerce"
            )
            .fillna(0)
            .tolist()
        )

    except Exception:
        pass


# ============================================================================
# SUMMARY OBJECT
# ============================================================================

summary = {

    "status":
        status,

    "requests":
        int(total_requests),

    "failures":
        int(total_failures),

    "error_rate_percent":
        round(error_rate, 2),

    "throughput_rps":
        round(total_rps, 2),

    "average_response_ms":
        round(avg_response, 2),

    "p95_ms":
        round(p95, 2),

    "p99_ms":
        round(p99, 2),

    "violations":
        violations,

    "slowest_endpoints":
        slowest_rows,

    "failing_endpoints":
        worst_rows
}


# ============================================================================
# JSON OUTPUT
# ============================================================================

with open(
    OUTPUT_JSON,
    "w",
    encoding="utf-8"
) as fp:

    json.dump(
        summary,
        fp,
        indent=4
    )

print()
print(
    f"JSON report created: "
    f"{OUTPUT_JSON}"
)


# ============================================================================
# MARKDOWN OUTPUT
# ============================================================================

markdown = f"""
# Performance Report

## Summary

| Metric | Value |
|----------|----------|
| Status | {status} |
| Requests | {int(total_requests)} |
| Failures | {int(total_failures)} |
| Error Rate | {error_rate:.2f}% |
| Throughput | {total_rps:.2f} req/s |
| Average Response | {avg_response:.2f} ms |
| P95 | {p95:.2f} ms |
| P99 | {p99:.2f} ms |

## SLA Validation

"""

if violations:

    for violation in violations:

        markdown += (
            f"- {violation}\n"
        )

else:

    markdown += (
        "- No violations detected\n"
    )

markdown += (
    "\n## Top Slow Endpoints\n\n"
)

for endpoint in slowest_rows:

    markdown += (
        f"- {endpoint['endpoint']}"
        f" : "
        f"{endpoint['avg_ms']:.2f} ms\n"
    )

markdown += (
    "\n## Top Failing Endpoints\n\n"
)

if worst_rows:

    for endpoint in worst_rows:

        markdown += (
            f"- {endpoint['endpoint']}"
            f" : "
            f"{endpoint['failures']:.0f}"
            f" failures\n"
        )

else:

    markdown += (
        "- No failing endpoints\n"
    )

with open(
    OUTPUT_MD,
    "w",
    encoding="utf-8"
) as fp:

    fp.write(markdown)

print(
    f"Markdown report created: "
    f"{OUTPUT_MD}"
)


# ============================================================================
# PART 3 CONTINUES HERE
# ============================================================================

# ============================================================================
# HTML OUTPUT
# ============================================================================

html = f"""
<!DOCTYPE html>
<html>

<head>

<meta charset="utf-8">

<title>
Locust Performance Report
</title>

<script src="https://cdn.jsdelivr.net/npm/chart.js"></script>

<style>

body {{
    font-family: Arial, sans-serif;
    margin: 40px;
    background-color: #f7f8fa;
}}

.pass {{
    color: #28a745;
}}

.fail {{
    color: #dc3545;
}}

.card {{
    background: white;
    border-radius: 8px;
    padding: 20px;
    margin-bottom: 30px;
    box-shadow:
        0 2px 8px
        rgba(0,0,0,0.08);
}}

.metric {{
    font-size: 18px;
    margin-bottom: 10px;
}}

.section-title {{
    margin-bottom: 20px;
}}

canvas {{
    max-width: 1400px;
}}

table {{
    border-collapse: collapse;
    width: 100%;
}}

table th,
table td {{
    border: 1px solid #ddd;
    padding: 8px;
}}

table tr:nth-child(even) {{
    background-color: #f5f5f5;
}}

table th {{
    background-color: #2196f3;
    color: white;
}}

.kpi-grid {{
    display: grid;
    grid-template-columns:
        repeat(
            auto-fit,
            minmax(
                220px,
                1fr
            )
        );

    gap: 16px;
}}

.kpi {{
    border-radius: 6px;
    padding: 16px;
    background: #f8f9fa;
}}

.kpi-value {{
    font-size: 28px;
    font-weight: bold;
}}

.kpi-label {{
    color: #444;
}}

ul {{
    line-height: 1.8;
}}

</style>

</head>

<body>

<h1>
Locust Performance Report
</h1>

<h2 class="{status.lower()}">
Status: {status}
</h2>

<div class="card">

<h2 class="section-title">
Execution Summary
</h2>

<div class="kpi-grid">

<div class="kpi">

<div class="kpi-value">
{int(total_requests)}
</div>

<div class="kpi-label">
Requests
</div>

</div>

<div class="kpi">

<div class="kpi-value">
{int(total_failures)}
</div>

<div class="kpi-label">
Failures
</div>

</div>

<div class="kpi">

<div class="kpi-value">
{error_rate:.2f}%
</div>

<div class="kpi-label">
Error Rate
</div>

</div>

<div class="kpi">

<div class="kpi-value">
{total_rps:.2f}
</div>

<div class="kpi-label">
Requests/sec
</div>

</div>

<div class="kpi">

<div class="kpi-value">
{avg_response:.0f} ms
</div>

<div class="kpi-label">
Average Response
</div>

</div>

<div class="kpi">

<div class="kpi-value">
{p95:.0f} ms
</div>

<div class="kpi-label">
P95
</div>

</div>

<div class="kpi">

<div class="kpi-value">
{p99:.0f} ms
</div>

<div class="kpi-label">
P99
</div>

</div>

</div>

</div>

<div class="card">

<h2 class="section-title">
SLA Validation
</h2>

<ul>
"""

if violations:

    for violation in violations:

        html += f"""
<li>
❌ {violation}
</li>
"""

else:

    html += """
<li>
✅ No SLA violations detected
</li>
"""

html += f"""

</ul>

</div>

<div class="card">

<h2 class="section-title">
Performance Overview
</h2>

<canvas
    id="overviewChart">
</canvas>

</div>

<div class="card">

<h2 class="section-title">
Top Slow Endpoints
</h2>

<canvas
    id="slowEndpointsChart">
</canvas>

</div>

<div class="card">

<h2 class="section-title">
Top Failing Endpoints
</h2>

<canvas
    id="failingEndpointsChart">
</canvas>

</div>
"""

# ============================================================================
# HISTORY CHARTS
# ============================================================================

html += f"""

<div class="card">

<h2 class="section-title">
Response Time Over Time
</h2>

<canvas
    id="responseTimeHistoryChart">
</canvas>

</div>

<div class="card">

<h2 class="section-title">
Requests Per Second Over Time
</h2>

<canvas
    id="rpsHistoryChart">
</canvas>

</div>

<div class="card">

<h2 class="section-title">
Failures Over Time
</h2>

<canvas
    id="failuresHistoryChart">
</canvas>

</div>

<div class="card">

<h2 class="section-title">
Detailed Statistics
</h2>

{stats.to_html(index=False)}

</div>

<script>

//
// Performance Overview
//

new Chart(

    document.getElementById(
        "overviewChart"
    ),

    {{

        type: "bar",

        data: {{

            labels: [
                "P95",
                "P99",
                "Error %",
                "Req/s"
            ],

            datasets: [{{
                label:
                    "Performance KPIs",

                data: [
                    {p95},
                    {p99},
                    {error_rate},
                    {total_rps}
                ],

                backgroundColor: [
                    "#2196F3",
                    "#4CAF50",
                    "#FF9800",
                    "#9C27B0"
                ]
            }}]
        }}
    }}
);

//
// Top Slow Endpoints
//

new Chart(

    document.getElementById(
        "slowEndpointsChart"
    ),

    {{

        type: "bar",

        data: {{

            labels:
                {json.dumps(slow_labels)},

            datasets: [{{

                label:
                    "Average Response Time (ms)",

                data:
                    {json.dumps(slow_values)},

                backgroundColor:
                    "#F44336"

            }}]

        }},

        options: {{
            indexAxis: "y"
        }}

    }}

);

//
// Top Failing Endpoints
//

new Chart(

    document.getElementById(
        "failingEndpointsChart"
    ),

    {{

        type: "bar",

        data: {{

            labels:
                {json.dumps(failure_labels)},

            datasets: [{{

                label:
                    "Failures",

                data:
                    {json.dumps(failure_values)},

                backgroundColor:
                    "#FF9800"

            }}]

        }},

        options: {{
            indexAxis: "y"
        }}

    }}

);

//
// Response Time History
//

new Chart(

    document.getElementById(
        "responseTimeHistoryChart"
    ),

    {{

        type: "line",

        data: {{

            labels:
                {json.dumps(history_timestamps)},

            datasets: [{{

                label:
                    "Response Time",

                data:
                    {json.dumps(history_response_time)},

                borderColor:
                    "#2196F3",

                fill: false

            }}]

        }}

    }}

);

//
// Throughput History
//

new Chart(

    document.getElementById(
        "rpsHistoryChart"
    ),

    {{

        type: "line",

        data: {{

            labels:
                {json.dumps(history_timestamps)},

            datasets: [{{

                label:
                    "Requests/sec",

                data:
                    {json.dumps(history_rps)},

                borderColor:
                    "#4CAF50",

                fill: false

            }}]

        }}

    }}

);

//
// Failures History
//

new Chart(

    document.getElementById(
        "failuresHistoryChart"
    ),

    {{

        type: "line",

        data: {{

            labels:
                {json.dumps(history_timestamps)},

            datasets: [{{

                label:
                    "Failures/sec",

                data:
                    {json.dumps(history_failures)},

                borderColor:
                    "#F44336",

                fill: false

            }}]

        }}

    }}

);

</script>

</body>
</html>
"""

# ============================================================================
# WRITE HTML
# ============================================================================

with open(
    OUTPUT_HTML,
    "w",
    encoding="utf-8"
) as fp:

    fp.write(html)

print(
    f"HTML report created: "
    f"{OUTPUT_HTML}"
)


# ============================================================================
# FINAL CONSOLE REPORT
# ============================================================================

print()
print("=" * 80)
print("FINAL PERFORMANCE SUMMARY")
print("=" * 80)

print(
    f"Status            : {status}"
)

print(
    f"Requests          : "
    f"{int(total_requests)}"
)

print(
    f"Failures          : "
    f"{int(total_failures)}"
)

print(
    f"Error Rate        : "
    f"{error_rate:.2f}%"
)

print(
    f"Throughput        : "
    f"{total_rps:.2f} req/s"
)

print(
    f"Average Response  : "
    f"{avg_response:.2f} ms"
)

print(
    f"P95               : "
    f"{p95:.2f} ms"
)

print(
    f"P99               : "
    f"{p99:.2f} ms"
)

print()

if violations:

    print("SLA Violations:")

    for violation in violations:

        print(
            f" - {violation}"
        )

else:

    print(
        "No SLA violations detected."
    )

print("=" * 80)

print(
    f"JSON Report : {OUTPUT_JSON}"
)

print(
    f"Markdown    : {OUTPUT_MD}"
)

print(
    f"HTML Report : {OUTPUT_HTML}"
)

print("=" * 80)


# ============================================================================
# CI/CD QUALITY GATE
# ============================================================================

if status == "FAIL":

    print()
    print(
        "Performance Quality Gate FAILED"
    )

    sys.exit(1)

print()
print(
    "Performance Quality Gate PASSED"
)

sys.exit(0)

--- 
Execution: locust \
--headless \
-u 100 \
-r 10 \
--run-time 10m \
--csv reports/run

Depois python tools/analyze_results.py

Saídas geradas:
reports/
├── summary.json
├── summary.md
└── summary.html

---

# Security Testing Cheatsheet
## OWASP ZAP + Burp Suite

#table-of-contents

---

# Security Testing Workflow

```text
Reconnaissance
    ↓
Authentication
    ↓
Traffic Capture
    ↓
Passive Analysis
    ↓
Authorization Testing
    ↓
Input Validation Testing
    ↓
Active Security Testing
    ↓
Reporting
```

---

# OWASP ZAP

## Start ZAP

Linux:

```bash
zap.sh
```

---

Windows:

```bash
zaproxy.exe
```

---

# Configure Browser Proxy

```text
Host:
127.0.0.1

Port:
8080
```

---

Traffic Flow

```text
Browser
      ↓
 OWASP ZAP
      ↓
 Application
```

---

# ZAP Passive Scan

Safe for:

```text
Development

Testing

Production
```

---

Detects:

```text
Missing Security Headers

Information Disclosure

Weak Cookies

TLS Problems
```

---

# Run Passive Scan

```text
Browse Application
```

↓

```text
Review Alerts
```

---

Common Findings:

```text
Missing CSP

Missing X-Frame-Options

Cookie Missing HttpOnly

Cookie Missing Secure
```

---

# ZAP Active Scan

Performs:

```text
XSS Testing

SQL Injection Testing

Authentication Testing

Input Validation Testing
```

---

Start:

```text
Right Click Target

Attack

Active Scan
```

---

# ZAP Spider

## Traditional Spider

```text
Links
Pages
URLs
```

---

## AJAX Spider

For:

```text
React

Angular

Vue

Single Page Applications
```

---

# ZAP API Testing

Import:

```text
OpenAPI

Swagger

Postman Collection
```

---

Menu:

```text
Import

OpenAPI Definition
```

---

# Baseline Scan

Safe CI/CD Scan.

Docker:

```bash
docker run \
owasp/zap2docker-stable \
zap-baseline.py \
-t https://target.site
```

---

Output:

```text
HTML

XML

JSON
```

---

# Full Scan

```bash
zap-full-scan.py
```

Includes:

```text
Spider

Passive Scan

Active Scan
```

---

Not recommended for Production.

---

# API Scan

```bash
zap-api-scan.py
```

Designed for:

```text
REST

OpenAPI

Swagger
```

---

# ZAP Docker

```bash
docker pull \
owasp/zap2docker-stable
```

---

Run:

```bash
docker run \
owasp/zap2docker-stable
```

---

# ZAP CI/CD

## Azure DevOps

```yaml
- script: |
    zap-baseline.py \
    -t https://test.server
```

---

## GitHub Actions

```yaml
- run: |
    zap-baseline.py \
    -t https://test.server
```

---

# Burp Suite

# Start Burp

```text
Burp Suite Community
```

or

```text
Burp Suite Professional
```

---

# Burp Proxy

Purpose:

```text
Capture Traffic
```

---

Flow:

```text
Browser
     ↓
Burp Proxy
     ↓
Application
```

---

# Configure Browser

```text
Host:
127.0.0.1

Port:
8080
```

---

# Intercept

Enable:

```text
Proxy

Intercept

Intercept On
```

---

Captured Request:

```http
POST /login
```

---

Modify:

```text
Headers

Cookies

Tokens

Payload
```

---

Forward:

```text
Forward
```

---

# HTTP History

Menu:

```text
Proxy

HTTP History
```

---

Contains:

```text
All Requests

All Responses
```

---

Useful for:

```text
Reproducing Bugs

Security Analysis

API Testing
```

---

# Repeater

Most used Burp feature.

---

Send Request:

```text
Right Click

Send To Repeater
```

---

Modify:

```text
Parameters

Headers

Cookies

JWT
```

---

Execute:

```text
Send
```

---

# Repeater Example

Original:

```http
GET /api/documents
```

---

Modify:

```http
Authorization:
Bearer invalid-token
```

---

Expected:

```http
401 Unauthorized
```

---

# Intruder

(Professional Version)

Purpose:

```text
Automated Payload Testing
```

---

Examples:

```text
User Enumeration

Input Validation

Authorization Testing
```

---

# Intruder Attack Types

## Sniper

```text
One Variable
```

---

## Battering Ram

```text
Same Payload Everywhere
```

---

## Pitchfork

```text
Multiple Payload Lists
```

---

## Cluster Bomb

```text
All Combinations
```

---

# Sequencer

Purpose:

```text
Session Token Analysis
```

---

Tests:

```text
Randomness

Predictability

Entropy
```

---

Useful Tokens:

```text
JSESSIONID

JWT

Access Tokens
```

---

# Decoder

Supports:

```text
Base64

URL

Hex

JWT

Unicode
```

---

Example:

```text
VGVzdA==
```

↓

```text
Test
```

---

# Comparer

Compare:

```text
Request A

vs

Request B
```

---

Useful for:

```text
Different Roles

Different Permissions

Different Sessions
```

---

# Extensions

## Install

```text
BApp Store
```

---

# Recommended Extensions

## Autorize

Tests:

```text
Broken Access Control
```

---

Workflow:

```text
Admin Request
      ↓
Replay As User
      ↓
Compare Responses
```

---

## JWT Editor

Useful for:

```text
JWT Decoding

JWT Editing

JWT Validation
```

---

## Logger++

Improved:

```text
Traffic Logging
```

---

## Retire.js

Detects:

```text
Vulnerable
JavaScript Libraries
```

---

## SAML Raider

Most important for your environment.

Supports:

```text
SAML Requests

SAML Responses

RelayState

XML Signatures
```

---

# Authentication Testing

Verify:

```text
Login

Logout

Session Renewal

Token Refresh
```

---

For Roles:

```text
Creator

Publisher

Validator

Admin
```

Verify:

```text
Authorization

Visibility

Permissions
```

---

# SAML Analysis

Inspect:

```text
AuthnRequest

RelayState

SAMLResponse

Assertion
```

---

Useful Tools:

```text
Burp Repeater

SAML Raider

ZAP Proxy
```

---

# Session Testing

Inspect:

```text
Cookies

JWT

JSESSIONID
```

---

Validate:

```text
Expiration

Regeneration

Logout

Session Fixation
```

---

# API Security Testing

Verify:

```http
200

401

403

404
```

Responses.

---

Test:

```text
Authentication

Authorization

Input Validation
```

---

# Common Security Findings

## Broken Access Control

```text
User accesses Admin Endpoint
```

---

## Missing Authorization

```text
200

instead of

403
```

---

## Weak Session Management

```text
Predictable Session IDs
```

---

## Information Disclosure

```text
Stack Traces

Detailed Errors

Internal IDs
```

---

## Missing Security Headers

```text
Content-Security-Policy

X-Frame-Options

Strict-Transport-Security
```

---

# Security Headers Checklist

Verify:

```text
Content-Security-Policy

X-Frame-Options

X-Content-Type-Options

Strict-Transport-Security

Referrer-Policy

Permissions-Policy
```

---

# Security Testing Commands

## ZAP Baseline

```bash
zap-baseline.py \
-t https://target.site
```

---

## ZAP API Scan

```bash
zap-api-scan.py
```

---

## Docker Scan

```bash
docker run \
owasp/zap2docker-stable
```

---

# Daily Security Routine

```text
Capture Traffic
↓
Review Authentication
↓
Review Sessions
↓
Review Headers
↓
Run Passive Scan
↓
Test Authorization
↓
Review Findings
```

---

# Best Practices

✅

```text
Test As Multiple Roles
```

✅

```text
Review Security Headers
```

✅

```text
Validate Session Expiration
```

✅

```text
Automate Baseline Scans
```

✅

```text
Use Repeater Before Intruder
```

✅

```text
Integrate Security Into CI/CD
```

---

# Anti-Patterns

❌

```text
Testing Only Happy Paths
```

❌

```text
Ignoring Authorization
```

❌

```text
Using Admin For Everything
```

❌

```text
Ignoring Session Expiration
```

❌

```text
Skipping Passive Scan Findings
```

---

# Enterprise Workflow

```text
Locust
     ↓
Performance

Robot Framework
     ↓
Functional

OWASP ZAP
     ↓
Security Automation

Burp Suite
     ↓
Manual Security Validation

Azure DevOps
     ↓
Quality Gates
```

---

# Authentication Cheatsheet
## SAML + PKCE + RestAssured + Jsoup

#table-of-contents

---

# Authentication Architecture

Typical Flow:

```text
Client
   ↓
Service Provider (SP)
   ↓
Identity Provider (IdP)
   ↓
User Authentication
   ↓
SAML Assertion
   ↓
Session Establishment
   ↓
Authenticated User
```

---

# Core Components

## Service Provider (SP)

Application being accessed.

Examples:

```text
Eurosur

FADO

Enterprise Portal
```

---

## Identity Provider (IdP)

Performs authentication.

Examples:

```text
Microsoft Entra ID

ADFS

Keycloak

Okta
```

---

## User Agent

Traditionally:

```text
Browser
```

Automation:

```text
RestAssured
```

---

# Authentication Technologies

## SAML

```text
Security Assertion Markup Language
```

Provides:

```text
Single Sign-On

Federated Authentication
```

---

## PKCE

```text
Proof Key for Code Exchange
```

Protects:

```text
OAuth2 Authorization Code Flow
```

---

## RestAssured

Performs:

```text
HTTP Requests

Redirect Handling

Cookie Handling
```

---

## Jsoup

Parses:

```text
HTML

Forms

Hidden Inputs
```

---

# SAML Flow

```text
Application
      ↓
Redirect
      ↓
Identity Provider
      ↓
Login
      ↓
SAMLResponse
      ↓
Application
      ↓
Session Cookie
```

---

# Typical Redirect Chain

```http
GET /application
```

↓

```http
302 Found
```

↓

```http
Location:
https://idp.company.com
```

↓

```http
GET IdP
```

↓

```http
Login Form
```

---

# RestAssured Basics

## GET

```java
Response response =
    given()
    .when()
    .get(url);
```

---

## POST

```java
Response response =
    given()
        .formParams(params)
    .when()
        .post(url);
```

---

# Disable Auto Redirects

Important for SAML.

```java
Response response =
    given()
        .redirects()
        .follow(false)
    .when()
        .get(url);
```

---

# Read Redirect Header

```java
String location =
    response.getHeader(
        "Location"
    );
```

---

Useful for:

```text
Redirect Tracking

SAML Debugging
```

---

# Authentication Redirect Loop

Pattern:

```text
Application
 ↓
302
 ↓
IdP
 ↓
302
 ↓
Application
```

---

Track:

```java
Location
```

headers.

---

# PKCE Overview

Components:

```text
Code Verifier

Code Challenge

Authorization Code

Access Token
```

---

# PKCE Flow

```text
Code Verifier
      ↓
Code Challenge
      ↓
Authorization Request
      ↓
Authorization Code
      ↓
Token Exchange
      ↓
Access Token
```

---

# Generate Code Verifier

Example:

```java
String codeVerifier =
    UUID.randomUUID()
        .toString();
```

---

# Generate Code Challenge

Example:

```java
SHA256(codeVerifier)
```

↓

```text
Base64URL Encode
```

---

# Jsoup Basics

## Parse HTML

```java
Document document =
    Jsoup.parse(html);
```

---

# Extract Hidden Input

Example:

```html
<input
name="RelayState"
value="abc123"/>
```

---

Extract:

```java
String relayState =
    document
        .select(
            "input[name=RelayState]"
        )
        .val();
```

---

# Extract SAMLResponse

Example:

```html
<input
name="SAMLResponse"
value="..."
/>
```

---

Extract:

```java
String samlResponse =
    document
        .select(
            "input[name=SAMLResponse]"
        )
        .val();
```

---

# Most Useful Selectors

## By Name

```java
document.select(
    "input[name=username]"
);
```

---

## By ID

```java
document.select(
    "#username"
);
```

---

## By Type

```java
document.select(
    "input[type=hidden]"
);
```

---

# Hidden Fields Commonly Found

```text
SAMLResponse

RelayState

csrf

execution

lt
```

---

# Form Submission

Create Form Data:

```java
Map<String, String> form =
    new HashMap<>();
```

---

Add Fields:

```java
form.put(
    "RelayState",
    relayState
);
```

---

```java
form.put(
    "SAMLResponse",
    samlResponse
);
```

---

Submit:

```java
given()
    .formParams(form)
    .post(url);
```

---

# Cookie Management

## Extract Cookies

```java
Map<String,String> cookies =
    response.getCookies();
```

---

Example Cookies:

```text
JSESSIONID

AUTH

SESSION

SMSESSION
```

---

# Read Cookie

```java
String session =
    response.getCookie(
        "JSESSIONID"
    );
```

---

# Reuse Cookies

```java
given()
    .cookies(
        sessionCookies
    );
```

---

Benefit:

```text
No repeated authentication
```

---

# Session Reuse

Bad:

```text
Login
Login
Login
Login
```

---

Good:

```text
Login Once
     ↓
Reuse Session
```

---

# Session Validation

Request:

```java
GET /whoami
```

---

Expected:

```http
200 OK
```

---

Invalid Session:

```http
401 Unauthorized
```

---

# AuthenticationCalls Pattern

Recommended Architecture:

```java
AuthenticationCalls
```

---

Responsibilities:

```text
Login

Redirects

Cookies

PKCE

SAML

Session Reuse
```

---

# AuthenticationCalls Example

```java
AuthenticationCalls
    .authenticate(
        username,
        password
    );
```

---

Tests remain simple.

---

# AuthenticationContext Pattern

Avoid returning:

```java
String
```

---

Prefer:

```java
AuthenticationContext
```

---

Example:

```java
public class
AuthenticationContext {

    private Map<String,String>
        cookies;

    private String token;

}
```

---

# Benefits

```text
Reusable

Extensible

Future Proof
```

---

# BeforeSuite Authentication

Recommended:

```java
@BeforeSuite
```

---

Workflow:

```text
Authenticate Once
        ↓
Store Context
        ↓
Reuse In Tests
```

---

# RestAssured Authentication Request

```java
Response response =
    given()
        .cookies(cookies)
    .when()
        .get(url);
```

---

# Debugging Authentication

Verify:

```text
Redirect URL
```

↓

```text
RelayState
```

↓

```text
SAMLResponse
```

↓

```text
Cookies
```

↓

```text
Final Redirect
```

---

# Common Problems

## Missing RelayState

Symptoms:

```text
Unauthorized
```

---

Cause:

```text
RelayState not submitted
```

---

# Missing SAMLResponse

Cause:

```text
Hidden field not extracted
```

---

Verify:

```java
Jsoup selector
```

---

# Cookies Lost

Symptoms:

```text
Redirect loop
```

---

Cause:

```java
response.getCookies()
```

not reused.

---

# Session Expired

Symptoms:

```http
401 Unauthorized
```

---

Fix:

```text
Reauthenticate
```

---

# Redirect Loop

Symptoms:

```text
Login
↓
Redirect
↓
Login
↓
Redirect
```

---

Usually:

```text
Missing Cookie

Expired Session

Invalid RelayState
```

---

# Useful Response Methods

## Status Code

```java
response.statusCode();
```

---

## Response Body

```java
response.getBody()
    .asString();
```

---

## Headers

```java
response.getHeaders();
```

---

## Cookies

```java
response.getCookies();
```

---

# Logging

## Request Logging

```java
given()
    .log().all()
```

---

## Response Logging

```java
then()
    .log().all()
```

---

Useful during SAML debugging.

---

# Recommended Architecture

```text
Tests
     ↓
AuthenticationCalls
     ↓
AuthenticationContext
     ↓
RestAssured
     ↓
Identity Provider
```

---

# Daily Authentication Debug Workflow

```text
Capture Redirect
      ↓
Parse HTML
      ↓
Extract Hidden Inputs
      ↓
Submit Form
      ↓
Extract Cookies
      ↓
Validate Session
```

---

# Best Practices

✅

```text
Use RestAssured
```

✅

```text
Centralize Authentication
```

✅

```text
Reuse Sessions
```

✅

```text
Return AuthenticationContext
```

✅

```text
Follow Redirects Manually
```

✅

```text
Use Jsoup For Hidden Inputs
```

---

# Anti-Patterns

❌

```text
Authenticate Before Every Test
```

❌

```text
Store Credentials Everywhere
```

❌

```text
Hardcode Cookies
```

❌

```text
Mix Authentication Logic Into Tests
```

❌

```text
Ignore Redirect Chain
```

---

# Enterprise Authentication Workflow

```text
@BeforeSuite
       ↓
AuthenticationCalls
       ↓
AuthenticationContext
       ↓
Store Cookies
       ↓
Reuse Session
       ↓
Run Tests
       ↓
Validate Session
```

---

# Most Useful Snippets

## Extract RelayState

```java
document
    .select(
        "input[name=RelayState]"
    )
    .val();
```

---

## Extract SAMLResponse

```java
document
    .select(
        "input[name=SAMLResponse]"
    )
    .val();
```

---

## Read Cookies

```java
response.getCookies();
```

---

## Reuse Cookies

```java
given()
    .cookies(cookies)
```

---

## Authentication Context

```java
AuthenticationContext
```

---

## Authentication Service

```java
AuthenticationCalls
```

---