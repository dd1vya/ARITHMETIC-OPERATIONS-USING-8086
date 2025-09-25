# Arithmetic-operation-using-8086
# 8086 Assembly Language Programs for Arithmetic Operations

## AIM
To write and execute Assembly Language Programs to perform arithmetic operations for the 8086 microprocessor.

## APPARATUS REQUIRED
* Personal Computer with MASM Software
  
## 1. ADDITION
### Algorithm
1. Initialize memory location in HL register.
2. Store 1st data.
3. Increment HL to enter 2nd data.
4. Move 2nd number to accumulator.
5. Decrement HL.
6. Add value in memory with accumulator.
7. Store result.
8. Stop.

### FLOW CHART
<img width="707" height="1024" alt="image" src="https://github.com/user-attachments/assets/b5a7062d-e294-47cd-9683-a40de25e82de" />

## DIRECT ADDITION :
### Program
```asm
CODE SEGMENT
ASSUME CS: CODE, DS: CODE
ORG 1000H
MOV SI,2000H
MOV CL,00H
MOV AX,[SI]
MOV BX,[SI+02H]
ADD AX,BX
JNC L1
INC CL
L1:
MOV [SI+04H],AX
MOV [SI+06H],CL
MOV AH,4CH
INT 21H
CODE ENDS
END
```

### Output Table
| MEMORY LOCATION (INPUT) | MEMORY LOCATION (OUTPUT) |
| ----------------------- | ------------------------ |
|     1200                |      12                  |
|     1201                |      34                  |
|     1202                |      12                  |
|     1203                |      34                  |
|     1204                |      24                  |
|     1205                |      68                  |

### Manual Calculations :
![WhatsApp Image 2025-09-22 at 11 11 59_8fb6d2dd](https://github.com/user-attachments/assets/c690d087-cd55-4677-a753-e177704147a6)

### OUTPUT IMAGE FROM MASM SOFTWARE :
<img width="640" height="480" alt="Screenshot (60)" src="https://github.com/user-attachments/assets/7be1c82a-4059-4f6e-832a-dc7d82a4aba6" />

## INDIRECT ADDITION :
### PROGRAM : 
```
CODE SEGMENT 
ASSUME CS: CODE, DS:CODE 
ORG 1000H 
MOV SI,2000H 
MOV CL,00H 
MOV AX,[SI] 
MOV BX,[SI+02H] 
ADD AX,BX 
JNC L1 
INC CL 
L1:  MOV [SI+04H],AX 
MOV [SI+06H],CL 
MOV AH,4CH 
INT 21H 
CODE ENDS 
END

```
### OUTPUT TABLE :
| MEMORY LOCATION (INPUT) | MEMORY LOCATION (OUTPUT) |
| ----------------------- | ------------------------ |
|     1200                |      24                  |
|     1201                |      12                  |
|     1202                |      24                  |
|     1203                |      12                  |
|     1204                |      48                  |
|     1205                |      24                  |

### MANUAL CALCULATIONS :
![WhatsApp Image 2025-09-22 at 11 19 53_a1c790d4](https://github.com/user-attachments/assets/4033ef3b-7f65-4b4c-ae09-002bee0ba746)

### OUTPUT IMAGE FROM MASM SOFTWARE :
<img width="640" height="480" alt="Screenshot (67)" src="https://github.com/user-attachments/assets/0340d165-ea53-44cc-a738-1dc8e77bf2b1" />

## 2. SUBTRACTION
#### Algorithm
1. Initialize memory and store 1st data.
2. Increment to get 2nd data.
3. Move 2nd data to accumulator.
4. Subtract memory content.
5. Store result.

### FLOWCHART
<img width="578" height="797" alt="image" src="https://github.com/user-attachments/assets/564c3c7a-33ce-4a1c-8920-beb5c24b9b47" />

#### Program
```asm
CODE SEGMENT
ASSUME CS: CODE, DS: CODE
ORG 1000H
MOV SI,2000H
MOV CL,00H
MOV AX,[SI]
MOV BX,[SI+02H]
SUB AX,BX
JNC L1
INC CL
L1:
MOV [SI+04H],AX
MOV [SI+06H],CL
MOV AH,4CH
INT 21H
CODE ENDS
END
```
#### Output Table
| MEMORY LOCATION (INPUT) | MEMORY LOCATION (OUTPUT) |
| ----------------------- | ------------------------ |
|     1200                |      12                  |
|     1201                |      34                  |
|     1202                |      12                  |
|     1203                |      34                  |
|     1204                |      00                  |
|     1205                |      00                  |

#### Manual Calculations
![WhatsApp Image 2025-09-22 at 11 23 00_136dc50c](https://github.com/user-attachments/assets/2ab4505e-0926-4f05-9934-7669d9b31c77)

### OUTPUT SCREEN FROM MASM SOFTWARE :
![WhatsApp Image 2025-09-17 at 14 23 49_462c876e](https://github.com/user-attachments/assets/646153ff-3720-4e88-9f46-63875eb8170a)

## INDIRECT SUBTRACTION :
###PROGRAM :
```CODE SEGMENT 
ASSUME CS: CODE,DS:CODE 
ORG 1000H 
MOV SI,2000H 
MOV CL,00H 
MOV AX,[SI] 
MOV BX,[SI+02H] 
SUB AX, BX 
JNC DOWN 
INC CL 
DOWN: MOV [SI+04H],AX 
MOV [SI+06H],CL 
MOV AH,4CH 
INT 21H 
CODE ENDS 
END
```
### OUTPUT TABLE:
| MEMORY LOCATION (INPUT) | MEMORY LOCATION (OUTPUT) |
| ----------------------- | ------------------------ |
|     1200                |      12                  |
|     1201                |      34                  |
|     1202                |      12                  |
|     1203                |      34                  |
|     1204                |      00                  |
|     1205                |      00                  |

### MANUAL CALCULATION :
![WhatsApp Image 2025-09-22 at 11 25 06_e69403b4](https://github.com/user-attachments/assets/49368211-0573-424d-9c47-15ed4819321b)

### OUTPUT SCREEN FROM MASM SOFTWARE :
![WhatsApp Image 2025-09-22 at 09 00 30_1160c9f9](https://github.com/user-attachments/assets/107cad3e-9cd3-4f05-8fb8-f48cfbac7b57)

## 3. MULTIPLICATION
#### Algorithm
1. Initialize memory and store operands.
2. Move operands to registers.
3. Multiply.
4. Store result.

### FLOWCHART
<img width="569" height="906" alt="image" src="https://github.com/user-attachments/assets/88be88ff-2896-4a88-b73d-84ccffd2fcf9" />

#### Program
```asm
CODE SEGMENT
ASSUME CS: CODE, DS: CODE
ORG 1000H
MOV SI,2000H
MOV DX,0000H
MOV AX,[SI]
MOV BX,[SI+02H]
MUL BX
MOV [SI+04H],AX
MOV [SI+06H],DX
MOV AH,4CH
INT 21H
CODE ENDS
END
```

#### Output Table
| MEMORY LOCATION (INPUT) | MEMORY LOCATION (OUTPUT) |
| ----------------------- | -------------------------|
|     1200                |      12                  |
|     1201                |      34                  |
|     1202                |      12                  |
|     1203                |      34                  |
|     1204                |      09                  |
|     1205                |      5A                  |

#### Manual Calculations :
![WhatsApp Image 2025-09-22 at 11 29 02_6f91c896](https://github.com/user-attachments/assets/6e915b58-dc09-4205-9f52-e4579275674e)

#### OUTPUT SCREEN FROM MASM SOFTWARE :
---![WhatsApp Image 2025-09-22 at 09 52 15_3d1590cd](https://github.com/user-attachments/assets/5aed5e86-8275-403f-9e06-f3fa41d547ba)

## INDIRECT MULTIPLICATION :
### PROGRAM:
```CODE SEGMENT 
ASSUME CS: CODE,DS:CODE  
ORG 1000H 
MOV SI,2000H  
MOV DX,0000H 
 MOV AX,[SI] 
MOV BX,[SI+02H]  
MUL BX 
MOV [SI+04H],AX  
MOV [SI+06H],DX  
MOV AH,4CH 
INT 21H 
 CODE ENDS 
END
```
### OUTPUT TABLE :
| MEMORY LOCATION (INPUT) | MEMORY LOCATION (OUTPUT) |
| ----------------------- | -------------------------|
|     2000                |      12                  |
|     2001                |      34                  |
|     2002                |      12                  |
|     2003                |      34                  |
|     2004                |      44                  |
|     2005                |      51                  |
|     2006                |      97                  |
|     2007                |      0A                  |

#### Manual Calculations :
![WhatsApp Image 2025-09-22 at 11 31 46_c6eb8dcc](https://github.com/user-attachments/assets/e1b153ba-15e9-4690-97b5-a7a4492843e7)

### OUTPUT SCREEN FROM MASM SOFTWARE :
![WhatsApp Image 2025-09-22 at 09 11 38_3351edd6](https://github.com/user-attachments/assets/b7a61cc0-0988-4bcf-818d-fed1c849ef49)

## 4. DIVISION
#### Algorithm
1. Load memory location of operands.
2. Perform division.
3. Store result.

### FLOWCHART
<img width="1065" height="802" alt="image" src="https://github.com/user-attachments/assets/25b4a483-0d42-494b-8639-1af3ea17191b" />

#### Program
```asm
CODE SEGMENT
ASSUME CS: CODE, DS: CODE
ORG 1000H
MOV SI,2000H
MOV DX,0000H
MOV AX,[SI]
MOV BX,[SI+02H]
DIV BX
MOV [SI+04H],AX
MOV [SI+06H],DX
MOV AH,4CH
INT 21H
CODE ENDS
END
```

#### Output Table
| MEMORY LOCATION (INPUT) | MEMORY LOCATION (OUTPUT) |
| ----------------------- | ------------------------ |
|     2000                |      34                  |
|     2001|               |      12                  |
|     2002                |      34                  |
|     2003                |      12                  |
|     2004                |      01                  |
|     2005                |      00                  |

#### Manual Calculations :
![WhatsApp Image 2025-09-22 at 11 34 42_4094ca60](https://github.com/user-attachments/assets/45a6fad4-cc08-4805-a913-2bf3d50021f2)

## OUTPUT FROM MASM SOFTWARE :
![WhatsApp Image 2025-09-22 at 08 39 16_ac0336af](https://github.com/user-attachments/assets/44db926f-c50f-437d-b47d-d89fe445a644)

## INDIRECT DIVISION :
### PROGRAM :
```
CODE SEGMENT 
ASSUME CS: CODE,DS:CODE 
ORG 1000H 
MOV SI,2000H 
MOV DX,0000H 
MOV AX,[SI] 
MOV BX,[SI+02H] 
DIV BX 
MOV [SI+04H],AX 
MOV [SI+06H],DX 
MOV AH,4CH 
INT 21H 
CODE ENDS 
END
```

### OUTPUT TABLE :
| MEMORY LOCATION (INPUT) | MEMORY LOCATION (OUTPUT) |
| ----------------------- | ------------------------ |
|     2000                |      34                  |
|     2001|               |      12                  |
|     2002                |      34                  |
|     2003                |      12                  |
|     2004                |      01                  |
|     2005                |      00                  |

### MANUAL CALCULATIONS :
![WhatsApp Image 2025-09-22 at 11 36 53_c877ce96](https://github.com/user-attachments/assets/dd076954-cb1d-4905-a7b4-c973c18bb20b)

### OUTPUT FROM MASM SOFTWARE :
![WhatsApp Image 2025-09-22 at 09 27 18_30ecfa80](https://github.com/user-attachments/assets/85d47e9f-81ec-433f-a319-1c24cf95ebb9)

## RESULT
Thus, the Assembly Language Programs for 8086 to perform arithmetic operations (Addition, Subtraction, Multiplication, and Division) using both direct and indirect methods were successfully written and executed using MASM.

