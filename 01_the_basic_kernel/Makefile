all: kernel.bin

start.o: start.s
	nasm -f aout -o start.o start.s

kernel.bin: start.o
	ld -T link.ld -o kernel.bin start.o

clean:
	rm -f *.o kernel.bin
