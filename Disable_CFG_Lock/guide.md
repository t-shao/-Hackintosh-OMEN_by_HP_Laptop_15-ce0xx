1. Download UEFITool and IFR-Extractor. 
2. Open your firmware image in UEFITool and find CFG Lock unicode string. If it is not present, your firmware may not have this option and you should stop. 
3. Extract the Setup.bin PE32 Image Section (the one UEFITool found) through Extract Body menu option. 
4. Run IFR-Extractor on the extracted file (e.g. ./ifrextract Setup.bin Setup.txt). 
5. Find CFG Lock, VarStoreInfo (VarOffset/VarName): in Setup.txt and remember the offset right after it (e.g. 0x123).
6. Download and run Modified GRUB Shell compiled by brainsucker or use a newer version by datasone. 
7. Enter setup_var 0x123 0x00 command, where 0x123 should be replaced by your actual offset, and reboot. 