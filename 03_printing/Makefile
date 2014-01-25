OBJECTS = start.o main.o scrn.o

all: kernel.bin

.c.o:
	gcc -Wall -O -m32  -fstrength-reduce -fomit-frame-pointer -finline-functions -nostdlib -nostdinc -fno-builtin -c $< -o $@

.s.o:
	nasm -f elf  -o $@ $<

kernel.bin: $(OBJECTS)
	ld -m elf_i386  -T link.ld -o kernel.bin $(OBJECTS)

run: kernel.bin
	qemu-system-i386 -kernel kernel.bin -net none -m 8 -monitor stdio

clean:
	rm -f *.o kernel.bin
