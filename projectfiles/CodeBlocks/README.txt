README.txt

Compiling wesnoth on windows using CodeBlocks 10.05
(June 2011, development version 1.9.6+svn r49843,
earlier source versions untested)
updated: r50891, 2011-08-23
updated: 19.06.2013, untested

(Whenever you enter directories or names, you should do it
by using the "..." button to the right of the field.)
1. Get the source by downloading from from http://www.wesnoth.org/
or by using git (if you know how to). The folder where you put the
source is referred to as wesnoth_root/ in this README.
2. Install CodeBlocks http://www.codeblocks.org/
MinGw is not needed. CodeBlocks' installation folder is referred to as
codeblocks_root/ in this README.
3. Install tdm-gcc-4.5.2 from
http://sourceforge.net/projects/tdm-gcc/files/TDM-GCC Installer/Previous/1.1006.0/
Note that the projectfiles in wesnoth_root/projectfiles/CodeBlocks/
may contain the setting to compile with OpenMP so you should make sure
that this option is enabled while installing the compiler, there is a checkbox
for this in the installer. (Or simply make a "all packages" installation.)
The newest version of tdm-gcc won't work, you need the mentioned one.
4. In CodeBlocks, open
wesnoth_root/projectfiles/CodeBlocks/wesnoth.workspace
5. In CodeBlocks, goto (menu bar)>settings>compiler and debugger
>global compiler settings> (tab) toolchain executables.
In the field "compiler's installation directory", enter the folder
into which you did install tdm-gcc-4.5.2.
Into the fields "c compiler", "c++ compiler" and "linker for dynamic libs"
enter "g++.exe".
Into the field "linker for static libs", enter "ar.exe".
6. Download CodeBlocksWinSDK.zip from
http://www.mediafire.com/?qbibb8p3stb08w7 and extract
this archive so that you have directories codeblocks_root/include_tdm_gcc
and codeblocks_root/lib_tdm_gcc
Newer package versions can be downloaded from
http://sourceforge.net/projects/wesnoth/files/unofficial/Windows%20Compile%20Stuff/
They contain the usual needed headers/libs (.a files)/dlls combination; the exact directory
names may be different, so you need to adapt your settings in CodeBlocks which
reference them. Since dependencies may be added to wesnoth, older packages
may no longer work after some spot.
7. In CodeBlocks, goto (menu bar)>settings>compiler and debugger
>global compiler settings> (tab) search directories> (tab) compiler>Add.
Enter codeblocks_root/include_tdm_gcc.
8. In CodeBlocks, goto (menu bar)>settings>compiler and debugger
>global compiler settings> (tab) search directories> (tab) linker>Add.
Enter codeblocks_root/lib_tdm_gcc.
9. In CodeBlocks, choose (menu bar)>build>build workspace.
wesnoth.exe and wesnothd.exe should appear in wesnoth_root/
when finished building.
10. To be able to execute the program, copy all *.dll files from your
installation folder of the most recent official windows wesnoth development
release into wesnoth_root/.
