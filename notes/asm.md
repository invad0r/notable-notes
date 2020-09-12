---
tags: [c]
title: asm
created: '2019-07-30T06:19:48.988Z'
modified: '2020-09-02T17:33:49.395Z'
---

# asm

> assembly language - closely tied to processor architecture

- `CISC` Complex Instruction-Set Computer
- `RISC` Reduced Instruction-Set Computer
- `DSP` Digital Signal Processor
- `VLIW` Very Long Instruction Word

## usage
```asm
; opcode operands
add R1, R2, 3

; opcodes: arithmetic/logical
add
sub
mult
Cmp

; opcodes: memory load/store
ld
st

; opcodes: control transfer
jmp
bne

; opcodes: complex
movs


EAX,EBX,ECX,EDX - "general purpose", more or less interchangeable

lea  rbx, qword [..]

```

```c
unsigned long a1, r;

void junk( void ) {
   asm( "pushl %eax \n"
        "pushl %ebx \n"
        "movl $100,%eax \n"
        "movl a1,%ebx \n"
        "int $69 \n"
        "movl %eax,r \n"
        "popl %ebx \n"
        "popl %eax \n" );
}
```

## see also
- [[wasm]]
- [[c]]
- [[rust]]

