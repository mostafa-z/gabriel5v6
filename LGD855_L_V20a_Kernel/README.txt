1. Android build
  - Download original android source code ( L 5.0 ) from http://source.android.com
  - Untar opensource packages of LGD855_L_V20a_Android.tar.gz into downloaded android source directory
    a) cat LGD855_L_V20a_Android.tar.gza* | tar zxvpf -
  - And, merge the source into the android source code
  - Run following scripts to build android
    a) source build/envsetup.sh
    b) lunch
    c) make -j4
  - When you compile the android source code, you have to add google original prebuilt source(toolchain) into the android directory.
  - After build, you can find output at out/target/product/generic

2. Kernel Build  
  - Uncompress using following command at the android directory
        tar xvzf LGD855_L_V20a_Kernel.tar.gz  
  - When you compile the kernel source code, you have to add google original prebuilt source(toolchain) into the android directory.
  - Run following scripts to build kernel
    a) cd kernel
	b) make ARCH=arm CROSS_COMPILE=../prebuilts/gcc/linux-x86/arm/arm-eabi-4.8/bin/arm-eabi- g3-global_com-perf_defconfig zImage -j4
	
	* "-j4" : The number, 4, is the number of multiple jobs to be invoked simultaneously. 
  - After build, you can find the build image(zImage) at arch/arm/boot

3. how  to build chromium34_lge (vendor\lge\external\chromium34_lge\src),
   please refer to README.txt at the folder mentioned above.



