# My Additions
## The Syscall ```test```
Test is a syscall that calls itself using inline asm.
This was done in order to see what would happen if a syscall handler (within the kernel) called another syscall.

in the command line you can simply run:
```bash
$ test                              # the first time it won't call itself twice
calling test
sys_test called
not running syscall inside syscall
$ test                              # now it will call itself twice every time you call
calling test                        # this is being printed from user space
sys_test called                     # this is being printed from kernel space
running syscall inside syscall      # also from kernel space
sys_test called                     # same as before also kernel space
not running syscall inside syscall  # printed from kernel space
$ test
calling test
sys_test called
running syscall inside syscall
sys_test called
not running syscall inside syscall
```
