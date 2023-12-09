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
