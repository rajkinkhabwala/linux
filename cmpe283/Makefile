obj-m += cmpe283-1.o

all:
		make -C /lib/modules/$(shell uname -r)/build M=$(PWD) modules

clean:
		make -C /lib/modules/$(shell uname -r)/build M=$(PWD) clean

showmod:
		sudo insmod cmpe283-1.ko
		sudo rmmod cmpe283-1
		dmesg
