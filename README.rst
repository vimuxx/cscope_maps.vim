Install
=======

cs only
::

   curl https://raw.githubusercontent.com/vimuxx/cscope_maps.vim/master/cs -o /usr/local/bin/cs

or with cscope_maps.vim installed, see `.vim <https://github.com/vimuxx/.vim>`_
::

   ln -s ~/.vim/pack/foo/start/cscope_maps.vim/cs /usr/local/bin/cs

Usage
=====

::

   # cs help
   Usage:

          [KBUILD_ABS_SRCTREE=1] [SYMLINKS=1]   cs [dir/]         # for kernel
          [KBUILD_ABS_SRCTREE=1] [SYMLINKS=1]   cs find [dir/]
          [KBUILD_ABS_SRCTREE=1]                cs freebsd
          [KBUILD_ABS_SRCTREE=1] [SYMLINKS=1]   cs gn dir/
          [KBUILD_ABS_SRCTREE=1] [SYMLINKS=1]   cs llvm
          [KBUILD_ABS_SRCTREE=1] [SYMLINKS=1]   cs qemu
          [KBUILD_ABS_SRCTREE=1] [SYMLINKS=1]   cs uboot
          [KBUILD_ABS_SRCTREE=1] [SYMLINKS=1]   cs uefi

     make [KBUILD_ABS_SRCTREE=1] COMPILED_SOURCE=1 [O=dir/] cscope compile_commands.json
                                                            ↓              ↓
                                                            for cscope     for clangd
