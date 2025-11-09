Emulator of the ternary digital electronic machine 'SETUN' SETUN-1958 VM
====================================================================

A virtual machine of the ternary computer Setun, also known as "Small Automatic Digital Machine" written in C.

A virtual machine of the ternary digital computer "Setun" (also known as MCVM "Setun"), written in the C programming language.

## 1. History

- Creation date:            01.11.2018
- Last modified date:      27.10.2025
- Version:                   2.09
- Author:                    Vladimir V.
- E-mail:                   askfind@ya.ru


## 2. Building the SETUN-1958 emulator

```shell
$ cd ./Emulator-Setun-1958
$ make
gcc -v -std=gnu11 -o setun1958emu -g emusetun_test.c emusetun.c

$ ls -al ./setun1958emu
./setun1958emu
```

## 3. List of commands for the SETUN-1958 emulator virtual control panel

```shell
$ ./setun1958emu

Emulator ternary computer 'Setun-1958':
Version: 2.09
Author:  Vladimir V.
E-mail:  askfind@ya.ru

setun1958emu:
help
Commands control for setun1958emu:
dump     [arglist]
load     [l]    [arglist]
prn             [arglist]
debug    [d]    [arglist]
view     [v]
begin    [b]
pause    [p]
run      [r]
step     [s]    [arglist]
break    [br]   [arglist]
breakmb  [brm]  [arglist]
reg      [rg]   [arglist]
fram     [fr]   [arglist]
drum     [dr]   [arglist]
help     [h]
quit     [q]
calc     [arglist]
```
## 3.0. 'calc' - calculator 'MK-Setun-01', using subroutine IP-2 for the SETUN-1958 emulator

```shell
$ ./setun1958emu

setun1958emu:
calc 12 / 13

MK-Setun-01
calc: 12.00000000 / 13.00000000 = 0.92307692

TODO: add codes for calculating trits!

setun1958emu:
```

## 3.1. 'dump' - command to print the file 'test1-fram-zone-0.txs', containing the source code of the SETUN-1958 emulator program

```shell
$ ./setun1958emu

setun1958emu:
dump ./software/test1/test1-fram-zone-0.txs

Read commands from file.txs: ./software/test1/test1-fram-zone-0.txs

[ Dump FRAM Setun-1958: ]
Zone = 0

WW WX  0 1Y Z0        02 03  Z 00 00
WY  0 11 0X           04  Z 01 00
WZ W0  1 01 X0        1W 1X  0 Z0 00
W1  1 1W X4           1Y  0 03 00
W2 W3  1 1W XY        1Z 10  0 0X 00
​​  W4  0 03 Z0           11  0 00 00
XW XX  0 2X 30        12 13  0 00 0Y
XY  0 12 Y3           14  1 ZW 22
XZ X0  Z WX 31        2W 2X  0 00 00
X1  0 1X Y0           2Y  0 00 00
X2 X3  0 12 33        2Z 20  0 00 0Y
X4  0 12 Y3           21  1 ZW 22
YW YX  0 1Y ZX        22 23  0 00 0Y
YY  0 X0 1X           24  1 YY YX
YZ Y0  0 Y4 13        3W 3X  0 00 00
Y1  0 04 Z0           3Y  0 00 00
Y2 Y3  0 X0 00        3Z 30  0 00 00
Y4  0 11 Z0           31  0 00 00
ZW ZX  0 2Z 3Y        32 33  0 00 00
ZY  0 Z3 10           34  0 00 00
ZZ Z0  0 00 2X        4W 4X  0 00 00
Z1  0 W0 00           4Y  0 00 00
Z2 Z3  0 10 ZX        4Z 40  0 00 00
Z4  0 WY 10           41  0 00 00
0W 0X  1 1Z XX        42 43  0 00 00
0Y  Z 1W XX           44  0 00 00
0Z 00  1 W3 00        KC     0 00 01
01  0 WX 00               Z Z2 1W

i=54

KC:
: [00000000+], 00001, (1)
: [-0-+-0+--], ZZ21W, (-7123)
-KC = 0-KC:
: [00000000-], 0000Z, (-1)
: [+0+-+0-++], 11YZ4, (7123)
```

## 3.2. 'load' or 'l' - reads source files in the directory './software/test1', containing the program source codes, and creates a virtual paper tape file 'paper.txt' in the directory './ptr1' for the SETUN-1958 emulator.

```shell
$ ./setun1958emu

Emulator ternary computer 'Setun-1958':
Version: 2.09
Author:  Vladimir V.I. 
E-mail:  askfind@ya.ru

setun1958emu:
load ./software/test2 ./ptr1
[ Convert software files to file paper.txt ]

Read file list: ./software/test2/test2.lst

Read file: test2-fram-zone-b.txs

Read file: test2-fram-zone-z.txs

Read file: test2-fram-zone-0.txs

Read file: test2-fram-zone-1.txs


Write file: ./ptr1/paper.txt

Script file source: ./software/test2/script.sst

Script file destination: ./script/script.sst

Copy file source to file destination.

setun1958emu:
begin

setun1958emu:

[ Start Setun-1958 ]

TECT2
<STOP>

[ Script file: 'script.sst' ]
Address: [0+++-+], 14Y, (115)
Note:   Success!
``` New address: [000000], 000, (0)
Action: R

K  : [0+0+-+--0], 0322X, (2364)
F  : [-----], ZWW, (-121)
C  : [+++-+], 14Y, (115)
W  : [+], 1, (1)
ph1: [0], 0, (0)
ph2: [0], 0, (0)
S  : [+-0-+00+0-+00+++-0], 2Z31Z314X, (82959585), {1.927199}
R  : [-0+0-00-+0-00-++00], X3XZ3XZ40, (-116427177), {-2.704670}
MB : [0000], 00, (0)


setun1958emu:
```

## 3.4. 'debug' or 'd' - debug mode for displaying the operation of the SETUN-1958 emulator

```shell
$ ./setun1958emu

setun1958emu:
debug 1
switch debug on

setun1958emu:
debug 0
switch debug off
```


## 3.5. 'view' or 'v' - displays all registers and status flags of the SETUN-1958 emulator

```shell
$ ./setun1958emu

setun1958emu:
view
[ View registers Setun-1958 ]

K  : [000000000], 00000, (0)
F  : [00000], 000, (0)
C  : [00000], 000, (0)
W  : [0], 0, (0)
ph1: [0], 0, (0)
ph2: [0], 0, (0)
S  : [000000000000000000], 000000000, (0), {
