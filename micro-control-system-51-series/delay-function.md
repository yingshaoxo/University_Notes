### 他们傻，你不能跟着他们傻

轮子就不要重复造了，特别是过时的轮子

So the basic function is :

```c
void delay(unix x) {
    TMOD = 0x01;
    TR0 = 1;
    while(x--) {
        TH0 = 0xfc;
        TL0 = 0x18;
        while(!TF0) {
        };
        TF0 = 0;
    }
    TR0 = 0;
}
```