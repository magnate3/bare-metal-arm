# run
```
root@ubuntu:~/arm/bare-metal-arm/src/chapter2# make system.bin
arm-none-eabi-gcc -c -g -mcpu=cortex-m3 -mthumb -o startup_lm3s6965.o startup_lm3s6965.c
arm-none-eabi-gcc -c -g -mcpu=cortex-m3 -mthumb -o uart_drv.o uart_drv.c
arm-none-eabi-gcc -c -g -mcpu=cortex-m3 -mthumb -o serial_print.o serial_print.c
arm-none-eabi-ld -T lm3s6965_layout.ld -o startup_lm3s6965.elf startup_lm3s6965.o uart_drv.o serial_print.o
arm-none-eabi-objcopy -O binary startup_lm3s6965.elf system.bin
root@ubuntu:~/arm/bare-metal-arm/src/chapter2# make run
qemu-system-arm -M lm3s6965evb -kernel system.bin -nographic -monitor telnet:127.0.0.1:1234,server,nowait 
Hello, World
...
Go on, say something...

```
