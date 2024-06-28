8bitworkshop_MMC3_siegegame
=====

[Open this project in 8bitworkshop](http://8bitworkshop.com/redir.html?platform=nes&githubURL=https%3A%2F%2Fgithub.com%2Fseanwiththebeard%2F8bitworkshop_MMC3_siegegame&file=siegegame.c).


This is an MMC3 conversion of the snake game sample to document some suggested changes to nesbanked.cfg and the vrambuf.c buffer size. On some emulators and real hardware, the MMC3 configuration has memory segment names that affect hardcoded startup code assignment of the stack pointer. Swapping the names of RAM and SRAM and putting everything in (system) RAM fixes the issue where the stack ends up in 0x8000. The vrambuffer size of 88 works better on some emulators and real hardware. Lastly, an extra memory segment is added and referenced in the code to move variables into the cartridge memory, with a macro added to set the MMC3 register to enable WRAM access called at the start of main()
