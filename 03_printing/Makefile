all: kernel.bin

start.o: start.asm
	nasm -f aout -o start.o start.asm

main.o:
	gcc -Wall -O -fstrength-reduce -fomit-frame-pointer -finline-functions -nostdinc -fno-builtin -c -o main.o main.c

scrn.o:
	gcc -Wall -O -fstrength-reduce -fomit-frame-pointer -finline-functions -nostdinc -fno-builtin -c -o scrn.o main.c

kernel.bin: start.o scrn.o main.o
	ld -T link.ld -o kernel.bin start.o

clean:
	rm -f *.o kernel.bin
