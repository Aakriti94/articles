# echo

* Write output to standard input


| Option      | Usage       | Example       |
| :-----:     |  :----      | :---          |
| `-n`        | Do not appened to a new line. The terminal curser will be in the same line as the output instead of being in a new line by default . | `[aaakriti@aakriti ~]$ echo -n "Harry Potter" ` <br /> `Harry Potter[aaakriti@aakriti ~]$ write your next command here`|
| `-e`        | enables interpretation of `\` backslash escapes        | Will be used in combination of `\` options      |
| `-E`        | Opposite of `-e`. Explicitly supress interpretation of backslash escapes       | Will be used in combination of `\` options   |
| `\a`   | Alert through Volume. Make sure your volume is high. It will ring a *ting* on an output        | `[aaakriti@aakriti ~]$ echo -e "\aHarry Potter"`  <br /> `Harry Potter`    |
| `\b`      | Backspace, removes all spaces between the texts       | `[aaakriti@aakriti ~]$ echo -e "Harry \bPotter"` <br /> `HarryPotter`   |
| `\b`   | It removes the n no. of character occurring before the `\b` used. Depending on the no. pf times used        | `[aaakriti@aakriti ~]$ echo -e "Harry\b\bPotter"`  <br /> `HarPotter`     |
| `\c`      | Suppress further output. Will not output whatever is written after `\c`       | `[aaakriti@aakriti ~]$ echo -e "Harry \c Potter is my favourite"` <br /> `Harry`   |
| `\e`      | Escape character. Omits the just next single character succeeding to `\e`      | `[aaakriti@aakriti ~]$ echo -e "\eHarry"` <br /> `arry`   |
| `\n`   | Creates a new line        | `[aaakriti@aakriti ~]$ echo -e "Harry \nPotter \nis \nmy \nfavourite"` <br /> `Harry` <br /> `Potter` <br /> `is` <br /> `my` <br /> `favourite`     |
| `\r`      | Carriage return. Will not return whatever is return before `\r`. opposite of `\c`    | `[aaakriti@aakriti ~]$ echo -e "Harry \r Potter is my favourite"` <br /> ` Potter is my favourite`   |
| `\t`   | Horizontal tabs. Use tabs as spaces.     |  ![Example](https://github.com/Aakriti94/articles/blob/master/linux-commands/Images/echo-t.jpg "Example")  |
| `\v`   | Vertical tab space. In a slanting manner       |  ![Example](https://github.com/Aakriti94/articles/blob/master/linux-commands/Images/echo-v.jpg "Example") |

## Other tricks

| Option      | Usage       |
| :-----    |  :----      |
| `echo *`   | Lists all files and folders        |
| `echo $x`      | echo value of a variable       |
| `\n + \t`   | new line + tab        |
| `\n + \v`  | new line + verticle tab  |
| `echo "Test" > testpage.log`  | will add contents to a file |
| 1. `echo 'Harry "Potter"'` <br /> 2. `echo "Harry \"Potter\""`  | `Harry "Potter"`  |
| `echo $(command)`  | Output of the command |
| `echo ~`  | home folder  |
| `echo {1..5}`  | `1 2 3 4 5`    |
| `echo $((50*2))`   |  `100`   |
| 1. `echo -e "\033[1;37mWHITE"` <br /> 2. `echo -e "\033[0;34mBLUE"` | Display in respective colors|

## Fun tricks

* Make someone get lost in dark black world of linux: ` echo -e "\033[0;30mBLACK"`
