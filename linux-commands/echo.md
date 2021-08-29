# echo

* Write output to standard input


| Option      | Usage       |
| :-----:     |  :----      |
| `-n`        | Do not appened to a new line. The terminal curser will be in the same line as the output instead of being in a new line by default. |
| `-e`        | enables interpretation of `\` backslash escapes        |
| `-E`        | Opposite of `-e`. Explicitly supress interpretation of backslash escapes       |
| `\a`   | Alert through Volume. Make sure your volume is high. It will ring a *ting* on an output        |
| `\b`      | Backspace, removes all spaces between the texts       |
| `\b`   | It removes the n no. of character occurring before the `\b` used. Depending on the no. of times used        | 
| `\c`      | Suppress further output. Will not output whatever is written after `\c`       |
| `\e`      | Escape character. Omits the just next single character succeeding to `\e`      |
| `\n`   | Creates a new line        |
| `\r`      | Carriage return. Will not return whatever is return before `\r`. opposite of `\c`    |
| `\t`   | Horizontal tabs. Use tabs as spaces.     |
| `\v`   | Vertical tab space. In a slanting manner       |

## Detailed options:
1. `-n` - Do not appened to a new line. The terminal curser will be in the same line as the output instead of being in a new line by default.
  ```sh
  [aaakriti@aakriti ~]$ echo -n "Harry Potter"
  Harry Potter[aaakriti@aakriti ~]$ write your next command here
  ```
2. `\a` - Alert through Volume. Make sure your volume is high. It will ring a ting on an output.
  ```sh
  [aaakriti@aakriti ~]$ echo -e "\aHarry Potter"
  Harry Potter
  ```
3. `\b` - Backspace, removes all spaces between the texts
  ```sh
  [aaakriti@aakriti ~]$ echo -e "Harry \bPotter"
  HarryPotter
  ```
4. `\b` - It removes the n no. of character occurring before the `\b` used. Depending on the no. of times used.
  ```sh
  [aaakriti@aakriti ~]$ echo -e "Harry\b\bPotter"
  HarPotter
  ```
5. `\c` - Suppress further output. Will not output whatever is written after `\c`
  ```sh
  [aaakriti@aakriti ~]$ echo -e "Harry \c Potter is my favourite"
  Harry
  ```
6. `\e` - Escape character. Omits the just next single character succeeding to `\e`
  ```sh
  [aaakriti@aakriti ~]$ echo -e "\eHarry"
  arry
  ```
7. `\n` - Creates a new line
  ```sh
  [aaakriti@aakriti ~]$ echo -e "Harry \nPotter \nis \nmy \nfavourite"
  Harry
  Potter
  is
  my
  favourite
  ```
8. `\r` - Carriage return. Will not return whatever is return before `\r`. opposite of `\c`
  ```sh
  [aaakriti@aakriti ~]$ echo -e "Harry \r Potter is my favourite"
  Potter is my favourite
  ```
9. `\t` - Horizontal tabs. Use tabs as spaces.
  ```sh
  [aaakriti@aakriti ~]$ echo -e "Harry \tpotter is my favourite"
  Harry   potter is my favourite

  [aaakriti@aakriti ~]$ echo -e "Harry \tpotter \tis \tmy \tfavourite"
  Harry   potter  is      my      favourite
  ```
10. `\v` - Vertical tab space. In a slanting manner.
  ```sh
  [aaakriti@aakriti ~]$  echo -e "Harry \v Potter"
  Harry
         Potter
  ```

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
