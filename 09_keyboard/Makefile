OBJECTS = scrn.o gdt.o idt.o isrs.o irq.o timer.o kb.o main.o start.o

all: kernel.bin

.c.o:
	gcc -Wall -O -fstrength-reduce -fomit-frame-pointer -finline-functions -nostdinc -fno-builtin -c $< -o $@

.s.o:
	nasm -f aout -o $@ $<

kernel.bin: $(OBJECTS)
	ld -T link.ld -o kernel.bin $(OBJECTS)

clean:
	rm -f *.o kernel.bin
