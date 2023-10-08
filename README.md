9872 Firmware disassembly
=========================

## Description

This repository holds the result of my disassembling and reverse-engineering of
HP9872C/T plotter firmware.  The main purpose of reverse-engineering was to
improve the fidelity of my 9872 simulator (see
[here](https://github.com/fulivi/mame_tools/tree/master/hp/9872)).

Firmware is stored in two 8k x 8 ROMs, one for the MSB and one for the LSB of
16-bit words.  It is executed by a HP proprietary 16-bit BPC processor (part
no. 1818-2500). This processor is the integer-only part that was also included in the
HP line of hybrid processors. They typically included BPC, IOP (I/O processor)
and EMC (floating point processor) on separate chips in the same package (hence
"hybrid").

In summary the plotter hardware has these characteristics:

  * 5 MHz BPC processor

  * 8k x 16 firmware ROM

  * 1k x 16 static RAM

  * A HPIB interface made of TTL ICs

  * Digital I/Os for buttons, LEDs, switches, etc.

  * The so-called interpolator driving the X & Y stepper motors

## Content

| *File*          | *Content*                                               |
|-----------------|---------------------------------------------------------|
| `9872c.bin`     | Full image of firmware. Words are in big-endian format. |
| `9872c.txt`     | Disassembly                                             |
| `1818-1741.BIN` | Image of LSB ROM                                        |
| `1818-1742.BIN` | Image of MSB ROM                                        |

## Acknowledgments

I'd like to thank Clay Archer for dumping the ROM image and making it available
[here](https://groups.io/g/VintHPcom/files/9872C%20Firmware).

