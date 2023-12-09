# QEMU TUTORIAL FOR WINDOWS 11

https://www.youtube.com/watch?v=cE6X2IrTzgU&list=PLmsony4NVQpxYb6B51t-uWWuGkph5rmf1&index=1

# DOWNLOAD LINKS

https://www.qemu.org/download/

# IMPORTANT LINKS

- https://www.qemu.org/docs/master/
- https://www.qemu.org/docs/master/system/introduction.html
- https://www.qemu.org/docs/master/interop/qemu-qmp-ref.html#qmp-ref

// install it
// add the path where u already installed qemu into env path
// check it with qemu-system-x86_64.exe

// start by creating a disk
---> qemu-img create -f qcow2 debian12.qcow2 20G
; explanations :

1. qemu-img -> syntax for creating the disk
2. qcow2 -> disk formats, there are other formats
3. 20g -> disk spaces that we set in ur directory of ur choice

the result of qemu-img create ... ->> Formatting 'demo.qcow2', fmt=qcow2 cluster_size=65536 extended_l2=off compression_type=zlib size=21474836480 lazy_refcounts=off refcount_bits=16

when we make the first qcow2 file the size is 193kb but why, we initiate it at 20g, cause there re no data in it yet and we need to reserve the spaces

// download ur operating system of ur choice

// in this demo im gonna use debian12 (stable is better right?)

// after that u need to copy the iso into the folder where u set up ur VM

some INFOS

### qemu-system-x86_64

- cpu base
  - // ->> cause idk what type of cpu i use, base is more convenient to use
- vga virtio
  - // virt_io --> common default in any linux distro
- display gtk,gl=on
  - // -->>
- machine type =q35,accel=hax
  - // -->> but can we not specify accel=hax ? i still not set up the intel haxm
  - // what is q35?
- device AC97
  - // -->> this device use the sound, the default AC97
- smp 2,sockets=2,cores=1,threads=1
  - // -->> the cores (processing)
  - // u need to know how many cores and socket that u re gonna apply
- boot d
  - // the boot section we have two kinds, hda and cdrom
- hda .\demo.qcow2 -m 4096 (or 2048)
  - // harddisk is in .\demo.qcow2 and memory 4096
- cdrom .\debian-12.2.0-amd64-netinst.iso
  - // since we default boot d, it means we will boot to cdrom
- usb
- device usb-tablet
  - // since i use laptop, use this, OPTIONAL?
- display default,show-cursor=on

```
qemu-system-x86_64 -cpu base -vga virtio -display gtk,gl=on -machine type=q35,accel=hax -device AC97 -smp 2,sockets=2,cores=1,threads=1 -hda .\demo.qcow2 -m 4096 -cdrom .\debian-12.2.0-amd64-netinst.iso -usb -device usb-tablet -display default,show-cursor=on
```

#### ---
