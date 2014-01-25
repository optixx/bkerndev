all: kernel.bin

start.o: start.asm
	nasm -f aout -o start.o start.asm

kernel.bin: start.o
	ld -T link.ld -o kernel.bin start.o

clean:
	rm -f *.o kernel.bin
