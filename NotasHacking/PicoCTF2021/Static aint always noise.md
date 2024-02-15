# PicoCTF2021
## Objetivo
Can you look at the data in this binary: [static](https://mercury.picoctf.net/static/ec4dbd8898ade34e1d60d5b70c1b8c8c/static)? This [BASH script](https://mercury.picoctf.net/static/ec4dbd8898ade34e1d60d5b70c1b8c8c/ltdis.sh) might help!

## Pistas
## Solucion
┌─[✗]─[oscar@oscar-parrot]─[~]
└──╼ $sh ltdis.sh static
Attempting disassembly of static ...
Disassembly successful! Available at: static.ltdis.x86_64.txt
Ripping strings from binary with file offsets...
Any strings found in static have been written to static.ltdis.strings.txt with file offset
┌─[oscar@oscar-parrot]─[~]
└──╼ 
┌─[✗]─[oscar@oscar-parrot]─[~]
└──╼ $./static -j
bash: ./static: Permiso denegado
┌─[✗]─[oscar@oscar-parrot]─[~]
└──╼ $chmod +x ./static
┌─[oscar@oscar-parrot]─[~]
└──╼ $./static -j
Oh hai! Wait what? A flag? Yes, it's around here somewhere!
┌─[oscar@oscar-parrot]─[~]
└──╼ $./static -h
Oh hai! Wait what? A flag? Yes, it's around here somewhere!
┌─[oscar@oscar-parrot]─[~]
└──╼ $strings ./static
/lib64/ld-linux-x86-64.so.2
libc.so.6
puts
__cxa_finalize
__libc_start_main
GLIBC_2.2.5
_ITM_deregisterTMCloneTable
__gmon_start__
_ITM_registerTMCloneTable
AWAVI
AUATL
[]A\A]A^A_
Oh hai! Wait what? A flag? Yes, it's around here somewhere!
;*3$"
picoCTF{d15a5m_t34s3r_98d35619}
GCC: (Ubuntu 7.5.0-3ubuntu1~18.04) 7.5.0
crtstuff.c
deregister_tm_clones
__do_global_dtors_aux
completed.7698
__do_global_dtors_aux_fini_array_entry
frame_dummy
__frame_dummy_init_array_entry
static.c
__FRAME_END__
__init_array_end
_DYNAMIC
__init_array_start
__GNU_EH_FRAME_HDR
_GLOBAL_OFFSET_TABLE_
__libc_csu_fini
_ITM_deregisterTMCloneTable
puts@@GLIBC_2.2.5
_edata
__libc_start_main@@GLIBC_2.2.5
__data_start
__gmon_start__
__dso_handle
_IO_stdin_used
__libc_csu_init
__bss_start
main
__TMC_END__
_ITM_registerTMCloneTable
flag
__cxa_finalize@@GLIBC_2.2.5
.symtab
.strtab
.shstrtab
.interp
.note.ABI-tag
.note.gnu.build-id
.gnu.hash
.dynsym
.dynstr
.gnu.version
.gnu.version_r
.rela.dyn
.rela.plt
.init
.plt.got
.text
.fini
.rodata
.eh_frame_hdr
.eh_frame
.init_array
.fini_array
.dynamic
.data
.bss
.comment
┌─[oscar@oscar-parrot]─[~]
└──╼ $
## Notas adicionales
Haciendo uso del script, se puede desmontar el static del archivo y usar string para poder leer el contenido 
## Referencias
https://computernewage.com/2019/01/13/scripting-linux-bash-crear-ejecutar-script/