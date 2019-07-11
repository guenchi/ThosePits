
# 关闭回显，缓冲，中断

```C
if (tcgetattr(0, &raw) == -1)
    return -1;

raw.c_lflag &= ~ECHO;
raw.c_lflag &= ~ICANON;
raw.c_lflag &= ~ISIG;

tcsetattr(0, TCSAFLUSH, &raw);
```


# 打开回显，缓冲，中断

```C
if (tcgetattr(0, &raw) == -1)
    return -1;

raw.c_lflag |= ECHO;
raw.c_lflag |= ICANON;
raw.c_lflag |= ISIG;

return tcsetattr(0, TCSAFLUSH, &raw);
```



# 终端控制键

```Scheme
上 : #\esc #\[ #\A

下 : #\esc #\[ #\B

右 : #\esc #\[ #\C

左 : #\esc #\[ #\D
```


# 终端Ctrl命令:

```Scheme
Ctrl + A : #\x01

Ctrl + B : #\x02

Ctrl + C : #\x03

Ctrl + D : #\x04

Ctrl + E : #\x05

Ctrl + F : #\x06

Ctrl + H : #\backspace

Ctrl + J : #\newline

Ctrl + K : #\vtab

Ctrl + L : #\page

Ctrl + M : #\newline

Ctrl + N : #\xE

Ctrl + P : #\x10

Ctrl + R : #\x12

Ctrl + T : #\x14

Ctrl + U : #\x15

Ctrl + V : #\x16

Ctrl + W : #\x17

Ctrl + X : #\x18

Ctrl + Y : #\x19

Ctrl + Z : #\x1A
```