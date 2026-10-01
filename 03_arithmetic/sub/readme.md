## Sub 1.asm

CF = 1: 50 < 80 as unsigned values, so the subtraction needs a borrow from beyond bit 7. This matches.
ZF = 0: the result 0xE2 is not zero. This matches.
SF = 1: bit 7 of 0xE2 (11100010) is 1, so the result reads as negative (-30). This matches.
OF = 0: as signed values, 50 - 80 = -30 fits in the range -128..127. Two positive operands can never overflow when subtracted. This matches.
AF = 0: the low nibbles are 0x2 - 0x0, which needs no borrow from bit 4. This matches.
PF = 0 observed, but 1 expected: PF looks at the low byte of the result. 0xE2 = 11100010 has four 1 bits (even parity), so SUB should set PF = 1.


