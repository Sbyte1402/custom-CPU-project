# custom-CPU-project

- Little Endian
- 8-bit processor


## Instruction set

| OP code |     Instruction     |                   Description                  |
| ------- |-------------------- | -----------------------------------------------|
| 0x0     | NOP                 | Do nothing, skips to next cycle.               |
| 0x1     | MOV Rd, Rs          | Copies the content of Rs in Rd.                |
| 0x2     | MVI Rd, Rs          | Loads an inmediate value of 8 bits in Rd.      |
| 0x3     | LDR Rd, [addr]      | Loads a RAM data in Rd.                        |
| 0x4     | STR Rs, [addr]      | Store Rs content in RAM.                       |
| 0x5     | PUSH Rs             | Store Rs content in stack.                     |
| 0x6     | POP Rd              | Draws a value from the Stack towards Rd.       |
| 0x7     | CMP Rd, Rs          | Compare Rd with Rs (only affects Flags).       |
| 0x8     | ADD Rd, Rs          | Rd = Rd + Rs.                                  |
| 0x9     | SUB Rd, Rs          | Rd = Rd - Rs.                                  |
| 0xA     | AND Rd, Rs          | AND logical operation.                         |
| 0xB     | OR Rd, Rs           | OR logical operation.                          |
| 0xC     | JMP[addr]           | Unconditional jump.                            |
| 0xD     | JZ[addr]            | Jump if the previous result was zero (Z = 1).  |
| 0xE     | JC[addr]            | Jump if there was hauling (C = 1).             |
| 0xF     | HLT                 | Stops the processor completely.                |

## Registers

|   Register   |  Binarie ID  |      Function      |
| -------------|  ----------- | ------------------ |
| R0           |      00      |  Main accumulator. |
| R1           |      01      |  Job Log/Loop c.   |
| R2           |      10      |  Job Log/Data p.   |
| R3           |      11      |  Job Log/Temp str. |
