At the heart of the console is the first active component: the CPU. It has access to all the passive
components. It can also perform operations on data, such as incrementing a number or applying a
bitwise operator. Its main job is to fetch and execute the instructions inside the ROM.
The PPU (Picture Processing Unit) is the second active component. It is responsible for displaying
graphics on the LCD. The PPU is not directly accessible, i.e. it cannot execute custom instructions
provided by the programmer. Instead, data is put into the VRAM (Video Random Access Memory)
and the OAM (Object Attribute Memory), and then a bunch of LCD-related I/O registers are set to
control the PPU behavior.
The WRAM (Work Random Access Memory) is a piece of memory in which data can be temporarily
stored. Its purpose is similar to the RAM on a regular PC. A typical usage could be to store a puzzle
board status or the number of lives of a player.
The HRAM (High Random Access Memory) is similar to the WRAM, in the sense that it can hold
temporary data. However, the DMG features special instructions to access the HRAM. These
instructions take less space in the ROM and execute faster than those that would target WRAM. The
catch is that the HRAM is very small, with only 127 bytes versus 8192 for the WRAM. For this
13
reason, the HRAM is better used for small subsets of data accessed very often, or as a scratchpad
memory.
The I/O (Input/Output) registers are used to communicate with the console’s internal devices. These
include the LCD, the joypad, the timers, the serial interface and the sound.
The IE component is a single 8-bit register used to enable interrupts. Interrupts correspond to
special events that require prompt attention from the programmer. There are five types of
interrupts, each with their own special purpose.
Figure 10 shows the motherboard of the DMG. The central component, labeled DMG-CPU, has a
misleading name. It actually contains the CPU, the PPU, the OAM, the I/O registers and the HRAM.
The VRAM and WRAM are outside the CPU. Interestingly, they are the same type of 8 KiB of RAM
from Sharp.