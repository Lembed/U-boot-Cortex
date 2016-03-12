

work stages:
 stage1 = > /cpu/arm_cortexm3/start.c   .start_armboot()
 stage2 = > /lib_arm/board.c            .main_loop()	
 stage3 = > /common/main.c              .
 
directionary:
/cpu/arm_cortexm3/, /lib_arm/, /board/stm/stm32f429discovery/
 The uboot start from the entery point _start(), which is set to the first program line by u-boot.lds in /cpu/arm_cortexm3/ directionary
 the _start() function of /cpu/arm_cortexm3/start.c initialiation the isr functions , disalbe the watch dog , diable the irq and then go to start_armboot() in /lib_arm/
 board.c file. the start_armboot() function initialization board adapter and soc interface components.

 The cpu initialization do gpio init, clock setup, timer setup, dram setup, cpuinfo print, those function location at /cpu/arm_corextm3/.
 the serial and ether adapter setup location at /driver/serial/ and /dirver/net/ directionary.

/include/configs/stm32f429discovery.h
 The stm32f429discovery.h file define the features of the board and cmds used.

/include/asm-arm/arch-stm32/
 Tt includes some variable and functions used by other board and cpu setup functions.



