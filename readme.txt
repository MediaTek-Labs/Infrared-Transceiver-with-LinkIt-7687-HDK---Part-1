/* Copyright Statement:
 *
 * (C) 2005-2016  MediaTek Inc. All rights reserved.
 *
 * This software/firmware and related documentation ("MediaTek Software") are
 * protected under relevant copyright laws. The information contained herein
 * is confidential and proprietary to MediaTek Inc. ("MediaTek") and/or its licensors.
 * Without the prior written permission of MediaTek and/or its licensors,
 * any reproduction, modification, use or disclosure of MediaTek Software,
 * and information contained herein, in whole or in part, shall be strictly prohibited.
 * You may only use, reproduce, modify, or distribute (as applicable) MediaTek Software
 * if you have agreed to and been bound by the applicable license agreement with
 * MediaTek ("License Agreement") and been granted explicit permission to do so within
 * the License Agreement ("Permitted User").  If you are not a Permitted User,
 * please cease any access or use of MediaTek Software immediately.
 * BY OPENING THIS FILE, RECEIVER HEREBY UNEQUIVOCALLY ACKNOWLEDGES AND AGREES
 * THAT MEDIATEK SOFTWARE RECEIVED FROM MEDIATEK AND/OR ITS REPRESENTATIVES
 * ARE PROVIDED TO RECEIVER ON AN "AS-IS" BASIS ONLY. MEDIATEK EXPRESSLY DISCLAIMS ANY AND ALL
 * WARRANTIES, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE IMPLIED WARRANTIES OF
 * MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE OR NONINFRINGEMENT.
 * NEITHER DOES MEDIATEK PROVIDE ANY WARRANTY WHATSOEVER WITH RESPECT TO THE
 * SOFTWARE OF ANY THIRD PARTY WHICH MAY BE USED BY, INCORPORATED IN, OR
 * SUPPLIED WITH MEDIATEK SOFTWARE, AND RECEIVER AGREES TO LOOK ONLY TO SUCH
 * THIRD PARTY FOR ANY WARRANTY CLAIM RELATING THERETO. RECEIVER EXPRESSLY ACKNOWLEDGES
 * THAT IT IS RECEIVER'S SOLE RESPONSIBILITY TO OBTAIN FROM ANY THIRD PARTY ALL PROPER LICENSES
 * CONTAINED IN MEDIATEK SOFTWARE. MEDIATEK SHALL ALSO NOT BE RESPONSIBLE FOR ANY MEDIATEK
 * SOFTWARE RELEASES MADE TO RECEIVER'S SPECIFICATION OR TO CONFORM TO A PARTICULAR
 * STANDARD OR OPEN FORUM. RECEIVER'S SOLE AND EXCLUSIVE REMEDY AND MEDIATEK'S ENTIRE AND
 * CUMULATIVE LIABILITY WITH RESPECT TO MEDIATEK SOFTWARE RELEASED HEREUNDER WILL BE,
 * AT MEDIATEK'S OPTION, TO REVISE OR REPLACE MEDIATEK SOFTWARE AT ISSUE,
 * OR REFUND ANY SOFTWARE LICENSE FEES OR SERVICE CHARGE PAID BY RECEIVER TO
 * MEDIATEK FOR SUCH MEDIATEK SOFTWARE AT ISSUE.
 */

/** 
  * @page Tutorial Part-1  IRRX example project
  * @{

@par Overview

  - Example description
   - This example is a reference application to demonstrate the usage of IRRX module APIs. 
   - This example doesn't require FreeRTOS.
 
 - Results
     - Log will show the the received IRRX data.
     - The received data is in an array format, it'll be used later to transmit data with IRTX module.

@par Hardware and software environment

   - Supported platform
     - LinkIt 7687 HDK.
     - IRRX Receiver.
     - Remote Controller.
  - HDK switches and pin configuration
    - IRRX transmitter mapping is listed below.
  |     CHx	        |GPIOx	|PINx  |
  |----------------	|-------|------|
  |  IRRX SINGNAL	|  34	|J35.2 |
  |  IRRX VCC	    |  NA	|J32.4 |
  |  IRRX GND	    |  NA	|J32.7 |


  - PC/environment configuration
   - A serial tool is required, such as hyper terminal, for UART logging.
   - COM port settings. baudrate: 115200, data bits: 8, stop bit: 1, parity: none and flow control: off.

@par Directory contents
  - Source and header files
   - mt7687_hdk/apps/ir_receive/src/main.c  			    Main program.
   - mt7687_hdk/apps/ir_receive/src/system_mt7687.c		    MT76x7 clock configuration file.
   - mt7687_hdk/apps/ir_receive/inc/hal_feature_config.h 	MT76x7 feature configuration file.
   - mt7687_hdk/apps/ir_receive/inc/flash_map.h		        MT76x7 memory layout symbol file.
   - mt7687_hdk/apps/ir_receive/GCC/startup_mt7687.s		MT76x7 startup file for GCC.
   - mt7687_hdk/apps/ir_receive/GCC/syscalls.c			    MT76x7 syscalls for GCC.
   - mt7687_hdk/apps/ir_receive/MDK-ARM/startup_mt7687.s    MT76x7's startup file for Keil.

  - Project configuration files using GCC
   - mt7687_hdk/apps/ir_receive/GCC/feature.mk		    	Feature configuration.
   - mt7687_hdk/apps/ir_receive/GCC/Makefile		 	Makefile.
   - mt7687_hdk/apps/ir_receive/GCC/mt7687_flash.ld		Linker script.

  - Project configuration files using Keil
   - mt7687_hdk/apps/ir_receive/MDK-ARM/ir_receive.uvprojx		uVision5 project file. Contains the project structure in XML format.
   - mt7687_hdk/apps/ir_receive/MDK-ARM/ir_receive.uvoptx		uVision5 project options. Contains the settings for the debugger, trace configuration, breakpoints, currently open files, etc.
   - mt7687_hdk/apps/ir_receive/MDK-ARM/flash.sct		                Linker script.

  - Project configuration files using IAR
   - mt7687_hdk/apps/ir_receive/EWARM/ir_receive.ewd		 IAR project options. Contains the settings for the debugger.
   - mt7687_hdk/apps/ir_receive/EWARM/ir_receive.ewp           IAR project file. Contains the project structure in XML format.
   - mt7687_hdk/apps/ir_receive/EWARM/ir_receive.eww           IAR workspace file. Contains project information.
   - mt7687_hdk/apps/ir_receive/EWARM/flash.icf			           Linker script.


@par Run the example
  - Connect the board to the PC with serial port cable.
  - Build the example project with a command "./build.sh mt7687_hdk ir_receive" from the SDK root folder and download the binary file to LinkIt 7687 HDK.
  - Run the example. The log will display the received raw IRRX data.

* @}
*/
