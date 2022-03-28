# S9_makepackage
This is tool to create fw package for S9/T9/R4 and other miner with 1387chip
before use this tool, must set an environment :
/home/rex/s9_makepackage

for example:
XILINX_PACKAGE_BASE_PATH=/home/XILINX/UBI/make-packages
export XILINX_PACKAGE_BASE_PATH

This project needs GnuPG configured and mtd utility, which support JFFS2 and UBI.

To create S9 package:
./makepackage 675 S9 user all merge auto gpg_password
The command line's output will show the position of fw package created.

1. 675: is the default freq value, But it is not used in auto freq mode miner.
2. S9: is the miner type, support: S9   T9    R4   T9+
3. user: is the package open to consumers.  (only can set "user" for fw package.)
4. all: is the control board type. all means support xilinx board and altera board.
5. merge: is used to combine the file system for upgrading usage with the normal miner's fw file system together, to fix some miner's failure on upgrade.
6. frequency type: fixed or auto frequency
7. gpg_password: is the password set when gpg key is created


There are only two application from bitmain: single-board-test and bmminer, which must be copied to app-bin subdir before make package.

The filesystem of linux and kernel can be complied from : https://github.com/eli-global-ph/setup-scripts/tree/angstrom-v2013.12-yocto1.5
