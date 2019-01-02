### 简单的事情我们简单的做

```c
void main() {
    EA = 1;
    EX0 = 1;
    IT0 = 1;
    while (1) {
    };
}

void when_it_comes() interrupt 0 {
    // do whatever you want when pin 3^2 get changed
}
```