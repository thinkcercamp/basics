# Setting up your environment

## Setup
### Installing VSCode
  - Mac/Apple
      - https://code.visualstudio.com/docs/setup/mac
  - Windows/PC
    - https://code.visualstudio.com/docs/setup/windows

### Installing Terminal Tools
  - Mac/Apple
    - https://www.iterm2.com/
  - Windows/PC
    - You will most likely need to install Git/Bash tool, please check in with one of your ThinkCERCAMP counselors to help out!
***

## So what the heck are we learning?
  - Regardless of what language we are writing code in, the internet compiles what we write down to three building blocks of the web
    - HTML
    - CSS
    - JavaScript (no relation to Java!)
  - We use certain tools and "compilers" for the browser to then translate what we write into one, two, or all of those three
  - Then those three get compiled down to even more technical machine code that our computers can read (all dem 0s and 1s)

## Vocabulary
  Term  | Definition
  ----  | ----
  Terminal/Command Line | The tool we use to access the skeleton/bones of our system. We can create, remove, move, edit, etc. files and folders all from within the terminal!
  HTML  | Hypertext Markup Language
  CSS | Cascading style sheets
  JavaScript |  One of the foundational languages that the browser reads (along with HTML and CSS)
  Markdown  | A language that allows us to mock/create files formatted such as this one without needing a formatting bar (bullet points, tables, bold, italics, etc...)
  Directory | A folder!
  Path | Either `relative` or `absolute` the path shows how to get from one file/folder to another
  Code Snippet | A little 'blurb' of code.  Feel free to write multi line code snippets in SLACK by surrounding your lines with triple-ticks (to the left of the 1 key) or single ticks for single-line snippets (ex: '\`'my first code snippet'\`' ➡ `my first code snippet` )

  "\```"
  multi
  line
  snippet
  "\```"
⬇
```
multi
line
snippet
```

## Let's Dig In!
  - When we code, often times we do so using a structure called "Pair Programming".  This allows us as developers (which you all are now!) to both 'drive' and 'navigate' while coding, essentially eliminating typos and providing immediate feedback to your pair.
  - VSCode provides tools like **Live Share** which allows teams to share control of screens and pair program in the same editor (this can be super helpful for remote folks as well!)

***

### Intro to Console and HTML (just a bit!)
  * Unix (Mac/Linux) and Windows have different versions of many of the same commands. In the following section those commands     will be listed in the following format: Unix/Windows. When only one command is listed, it is the same on both systems.
  - Open VSCode, and select 'New Terminal' in the 'terminal' menu
  - Terminal allows us to dig into the skeleton of our computers and create files and folders wherever we'd like in a snap!
    - To see where you currently are within your system type `pwd` (print working directory) in your terminal/command line
    - Typing `ls`/`dir` in your directory will 'list' every file and folder within it -
      - Our computers actually hold a number of hidden files as well, that help with memory and setup of our systems and projects.  To generate a list of all files and directories from your current location, use `ls -a` and notice the additional items that may begin with a `.`
    - `cd` stands for 'change directory' (that's what we call a folder) and can take a `path` to move from one place to another (`./` indicates your current directory, `../` goes up a directory)
    - `mkdir` allows you to create a new folder
    - `touch`/`edit` allows your create a new file from your console!
    - `mv`/`move` allows us to rename or move a file 
    -  `mv`/`rename` allows us to rename or move a directory
    - `rm`/`del` allows us to remove a file
    - `rm -rf`/ `rmdir` allows us to remove a directory
    - `history` will show us the recent history of our command line entries
    - There is no history command on Windows but you can use the up and down keys to scroll through recent commands
  - Alrighty, back to it! Using the commands above in your terminal, create a directory called `ThinkCERCAMP` on your Desktop with one file inside called `your_name_00.html`
  - Open the file in your VSCode editor, and begin typing an exclamation mark `!`.  You will see a prompt appear that leads you to an 'Emmett Abreviation', click tab. Walah! (Emmett is a tool built in to your version of VSCode that provides many shortcuts for commonly used code snippets)
  - Personalize the text inside your `<title>` tags to reflect your excitement! (this is the text that appears on your chrome tab when loading a web page!), and write "Hello World!" inside the `<body>` tags (don't worry if this all looks foreign to you, we'll do a much deeper dive into HTML and its properties and elements next session)
  - Visit this url (https://marketplace.visualstudio.com/items?itemName=techer.open-in-browser) to install an extention to allow you to open your file in the browser!
  - You did it! Right click on your html file in the file tree (the directory structure you see to your left) and select "Open in Default Browser"
  -Go back to your HTML file and change the "Hello World" text to say "Hello, my name is ___". Refresh your browser.

***
### Extension Activities:
  - [Learn More Bash and Scripting Tools](https://egghead.io/courses/automate-daily-development-tasks-with-bash)
***

[Ready to Move On? (Module 01)](../Module_01)

