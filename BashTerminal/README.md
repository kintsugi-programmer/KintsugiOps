# Bash & Terminal

## Introduction

- Terminal is just another CMD interface to interact with the computer, unlike GUI.
- Terminal will always be in a certain folder.
- Terminal is powerful and quick.
- **Tip:** If you don't have Linux, use **WSL (Windows Subsystem for Linux).**
- **Tip:** Just practice and build muscle memory.

---

## `pwd`

**Print Working Directory**

Shows the current directory, the path to the current folder.

### Example:

```bash
user@machine:~/Documents/BaliGit/KintsugiOps$ pwd
/home/kintsugi-programmer/Documents/BaliGit/KintsugiOps
user@machine:~/Documents/BaliGit/KintsugiOps$
```

### This is the base root directory:

```bash
user@machine:~$ pwd
/home/kintsugi-programmer
user@machine:~$
```

---

## `cd`

**Change Directory**

Navigate through your file system.

### Example: Going outside and inside a directory

```bash
user@machine:~/Documents/BaliGit/KintsugiOps$ cd ..
user@machine:~/Documents/BaliGit$ cd KintsugiOps
user@machine:~/Documents/BaliGit/KintsugiOps$
```

### Example: Navigating multiple folders at once

```bash
user@machine:~$ cd Documents/BaliGit/KintsugiOps
user@machine:~/Documents/BaliGit/KintsugiOps$
```

**Tip:** Use `TAB` to autocomplete folder names.

### Example: Use `TAB` to autocomplete folder names.

```bash
user@machine:~/Documents/BaliGit$ cd KintsugiOps/
```

### Example: Navigating multiple levels up

```bash
user@machine:~/Documents/BaliGit/KintsugiOps$ cd ../../..
user@machine:~$ ls
Desktop  Documents  Downloads  Music  Pictures  Public  snap  Templates  Videos
user@machine:~$
```

### Example: Navigating multiple levels down

```bash
user@machine:~/Documents/BaliGit/KintsugiOps$ cd ..
user@machine:~/Documents/BaliGit$ ls
KintsugiOps
user@machine:~/Documents/BaliGit$ cd ..
user@machine:~/Documents$ ls
BaliGit
user@machine:~/Documents$
```

### Example: Navigating to the home directory

```bash
user@machine:~/Documents/BaliGit/KintsugiOps$ cd
user@machine:~$ ls
Desktop  Documents  Downloads  Music  Pictures  Public  snap  Templates  Videos
user@machine:~$ pwd
/home/kintsugi-programmer
user@machine:~$
```

---

## `ls`

**List Files and Folders**

### Example: Basic listing

```bash
user@machine:~$ ls
Desktop  Documents  Downloads  Music  Pictures  Public  snap  Templates  Videos
user@machine:~$
```

### Example: Recursive listing

```bash
user@machine:~/Documents/BaliGit/KintsugiOps$ ls
hi.txt  meow.js  README.md  test  test1  test2  test3
```

```bash
user@machine:~/Documents/BaliGit/KintsugiOps$ ls -R
.:  
hi.txt  meow.js  README.md  test  test1  test2  test3  

./test:  

./test1:  
1.js  2.js  

./test2:  

./test3:
user@machine:~/Documents/BaliGit/KintsugiOps$
```

## `mkdir`

**Make Directory**

### Example: make single and multiple folders

```bash
user@machine:~/Documents/BaliGit/KintsugiOps$ mkdir test
user@machine:~/Documents/BaliGit/KintsugiOps$ ls
README.md  test
user@machine:~/Documents/BaliGit/KintsugiOps$ mkdir test1 test2 test3
user@machine:~/Documents/BaliGit/KintsugiOps$ ls
README.md  test  test1  test2  test3
user@machine:~/Documents/BaliGit/KintsugiOps$
```

---

## `touch`

**Create Any Type of Empty File**

### Example: make single/multiple empty files

```bash
user@machine:~/Documents/BaliGit/KintsugiOps$ touch hi.txt meow.js
user@machine:~/Documents/BaliGit/KintsugiOps$ ls
hi.txt  meow.js  README.md  test  test1  test2  test3
user@machine:~/Documents/BaliGit/KintsugiOps$
```

---

## `cat`

**Display Content of File**

### Example: cat a file

```bash
user@machine:~/Documents/BaliGit/KintsugiOps$ nano hi.txt
user@machine:~/Documents/BaliGit/KintsugiOps$ # I just wrote something
user@machine:~/Documents/BaliGit/KintsugiOps$ cat hi.txt
Hello World
I am kintsugi-programmer
;)
user@machine:~/Documents/BaliGit/KintsugiOps$
```

---

## `#comment`

**Comments Are Ignored by the Shell**

### Example: #comment

```bash
user@machine:~/Documents/BaliGit/KintsugiOps$ #hi
user@machine:~/Documents/BaliGit/KintsugiOps$
```

---


## `vi`

**Vim IDE - Complex but Fast**

### Example:

```bash
vi
# Press 'i' to enter insert mode
# Press 'esc' then type ':wq!' to save and exit
```

---

## `mv`

**Move Files from One Directory to Another**

### Example:

```bash
user@machine:~/Documents/BaliGit/KintsugiOps$ ls -R
.:
hi.txt  meow.js  README.md  test  test1  test2  test3

./test:

./test1:
1.js  2.js

./test2:

./test3:
user@machine:~/Documents/BaliGit/KintsugiOps$ mv test1/1.js test2/
user@machine:~/Documents/BaliGit/KintsugiOps$ ls -R
.:
hi.txt  meow.js  README.md  test  test1  test2  test3

./test:

./test1:
2.js

./test2:
1.js

./test3:
```

### Move all files from one directory to another

```bash
user@machine:~/Documents/BaliGit/KintsugiOps$ mv test1/* test2/
user@machine:~/Documents/BaliGit/KintsugiOps$ ls -R
.:
hi.txt  meow.js  README.md  test  test1  test2  test3

./test:

./test1:

./test2:
1.js  2.js

./test3:
```

### Move an entire folder

```bash
user@machine:~/Documents/BaliGit/KintsugiOps$ mv test1 test2/
user@machine:~/Documents/BaliGit/KintsugiOps$ ls -R
.:
hi.txt  meow.js  README.md  test  test2  test3

./test:

./test2:
1.js  2.js  test1

./test2/test1:

./test3:
user@machine:~/Documents/BaliGit/KintsugiOps$
```
---

## `cp`

**Copy Files**

- Use the `-r` flag to allow copying folders.

### Example:

```bash
user@machine:~/Documents/BaliGit/KintsugiOps$ ls -R
.:
1.js  2.js  hi.txt  meow.js  README.md  test  test1  test2  test3

./test:

./test1:

./test2:
1.js  2.js  test1

./test2/test1:

./test3:
user@machine:~/Documents/BaliGit/KintsugiOps$ cp -r ./* test
cp: cannot copy a directory, './test', into itself, 'test/test'
user@machine:~/Documents/BaliGit/KintsugiOps$ ls -R
.:
1.js  2.js  hi.txt  meow.js  README.md  test  test1  test2  test3

./test:
1.js  2.js  hi.txt  meow.js  README.md  test  test1  test2  test3

./test/test:
1.js  2.js  hi.txt  meow.js  README.md

./test/test1:

./test/test2:
1.js  2.js  test1

./test/test2/test1:

./test/test3:

./test1:

./test2:
1.js  2.js  test1

./test2/test1:

./test3:
```

---

## `clear`

**Clear the Terminal (Does Not Remove Anything)**

### Example:

```bash
user@machine:~/Documents/BaliGit/KintsugiOps$ clear
```

---

## `nvm`

**Node Version Manager**

Helps in installing Node.js on a machine.

- **Tip:** Just Google to install Node.js: [Node.js Download](https://nodejs.org/en/download)

### Example:

```bash
nvm current  # Should print the installed version

node -v  # Should print the installed Node.js version
npm -v   # Should print the installed npm version
```

---

## `node`

**Run Node.js in Terminal**

### Example:

```bash
user@machine:~/Documents/BaliGit/KintsugiOps$ node
Welcome to Node.js v20.18.0.
Type ".help" for more information.
>
```

### Example: Running JavaScript in Node.js

```bash
user@machine:~/Documents/BaliGit/KintsugiOps$ node
Welcome to Node.js v20.18.0.
Type ".help" for more information.
> let a = 2;
undefined
> console.log(a);
2
undefined
>
(To exit, press Ctrl+C again or Ctrl+D or type .exit)
>
user@machine:~/Documents/BaliGit/KintsugiOps$
```

### Running a JavaScript File

```bash
user@machine:~/Documents/BaliGit/KintsugiOps$ nano a.js
user@machine:~/Documents/BaliGit/KintsugiOps$ # wrote console.log("hi");
user@machine:~/Documents/BaliGit/KintsugiOps$ cat a.js
console.log("hi");
user@machine:~/Documents/BaliGit/KintsugiOps$ node a.js
hi
user@machine:~/Documents/BaliGit/KintsugiOps$ # similar to running the code
user@machine:~/Documents/BaliGit/KintsugiOps$
```

---

## `npm`

**Node Package Manager**

Used for installing packages, external dependencies, and libraries.

- **Tip:** [Publish JavaScript Code](https://www.npmjs.com/package/registry)
- **Tip:** [Search for npm Packages](https://www.npmjs.com/)

### Example:

```bash
user@machine:~/Documents/BaliGit/KintsugiOps$ npm install express

added 69 packages in 4s

14 packages are looking for funding
  run `npm fund` for details
user@machine:~/Documents/BaliGit/KintsugiOps$ ls
a.js  node_modules  package.json  package-lock.json  README.md
```

The `node_modules` folder contains external dependencies.

### Checking Installed Packages

```bash
user@machine:~/Documents/BaliGit/KintsugiOps$ cd node_modules/
user@machine:~/Documents/BaliGit/KintsugiOps/node_modules$ ls
express  mime  qs  debug  fresh  vary  send  serve-static  statuses
```

### Checking `package.json`

```bash
user@machine:~/Documents/BaliGit/KintsugiOps$ cat package.json
{
  "dependencies": {
    "express": "^4.21.2"
  }
}
```

---

## `man`

**View Command Manual**

The `man` command displays the manual for any command.

### Example:

```bash
man ls
```






[def]: #pwd