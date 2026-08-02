
# Building a CPU from scratch

The goal of this project is to learn and build from scratch a uP based on its own architecture, with the purpose of physically implementing the project in the future.

- 8 bits architecture
- RISC
- 16 bit instruction
    - `[4 bit opcode] [2 bit destination reg] [2 bit source reg] [8 bit value/reg]`
## ISA
### Data & memory

|  Opcode  |  Mnemonic  |     Description       |
| :------- | :--------- | :-------------------- |
| `0x0000` |    `NOP`   |  NOP                  |
| `0x0001` |   `LOADI`  |  LOADI Rd, #Inmediate |
| `0x0010` |   `LOAD`   |  LOAD Rd, [Ra]        |
| `0x0011` |   `STORE`  |  STORE [Ra], Rd       |

### Arithmetic
|  Opcode  |  Mnemonic  |     Description       |
| :------- | :--------- | :-------------------- |
| `0x0100` |    `ADD`   |  ADD Rd, Ra, Rb       |
| `0x0101` |    `SUB`   |  SUB Rd, Ra, Rb       |
| `0x0110` |    `INC`   |  INC Rd               |
| `0x0111` |    `DEC`   |  DEC Rd               |

### Logic
|  Opcode  |  Mnemonic  |     Description       |
| :------- | :--------- | :-------------------- |
| `0x1000` |    `AND`   |  AND Rd, Ra, Rb       |
| `0x1001` |    `OR`    |  OR Rd, Ra, Rb        |
| `0x1010` |    `NOT`   |  NOT Rd               |
| `0x1011` |    `FREE`  |                       |

### Workflow
|  Opcode  |  Mnemonic  |     Description       |
| :------- | :--------- | :-------------------- |
| `0x1100` |    `JUMP`  |  JMP #DIR             |
| `0x1101` |    `JZ`    |  JZ #DIR              |
| `0x1110` |   `JNZ`    |  JNZ #DIR             |
| `0x1111` |   `FREE`   |                       |

### Bits distribution
#### Type R (Register - Register) -> ADD, SUB, AND, OR
```
bits[15:12] -> opcode
bits[11:10] -> destiny reg (Rd)
bits[09:08] -> src reg A (Ra)
bits[07:06] -> src reg B (Rb)
bits[05:00] -> unassigned
```

#### Type U (Unary) -> INC, DEC, NOT
```
bits[15:12] -> opcode
bits[11:10] -> destiny/src reg (Rd)
bits[09:00] -> unassigned
```

#### Type I (Inmediate/Memory/Jumps) -> LOADI, LOAD, STORE,JUMP, JZ
```
bits[15:12] -> opcode
bits[11:10] -> destiny/address (Rd/Ra)
bits[09:08] -> source reg (ONLY for STORE, otherwise should be 0)
bits[07:00] -> unassigned
```
## Authors

- [@Sbyte1402](https://github.com/Sbyte1402)

