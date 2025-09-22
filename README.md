# Arithmetic Operation using 8086  
## 8086 Assembly Language Programs for Arithmetic Operations  

## AIM
To write and execute Assembly Language Programs to perform arithmetic operations for the 8086 microprocessor.  

## APPARATUS REQUIRED
- Personal Computer with MASM Software  

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

### Flowchart
![Flowchart for Addition](https://github.com/user-attachments/assets/b5a7062d-e294-47cd-9683-a40de25e82de)

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

#### Output Table

| MEMORY LOCATION (INPUT) | MEMORY LOCATION (OUTPUT) |
| ----------------------- | ------------------------ |
|                         |                          |
|      1201:34            |  68:1205                 |
|      1202:12            |  00:1206                 |
|      1203:34            |  c4:1207                 |                             

#### Manual Calculations

<img width="1280" height="717" alt="image" src="https://github.com/user-attachments/assets/62d1daed-fca4-4606-b725-53313c30d560" />




## OUTPUT IMAGE FROM MASM SOFTWARE
<img width="901" height="593" alt="Screenshot 2025-09-14 182139" src="https://github.com/user-attachments/assets/2a6ee828-4b7f-4a83-8650-138452df5eb4" />


<img width="916" height="593" alt="Screenshot 2025-09-14 175635" src="https://github.com/user-attachments/assets/ee533120-4050-4d87-8e57-b634b304935c" />


## 2. SUBTRACTION

### Algorithm

1. Initialize memory and store 1st data.
2. Increment to get 2nd data.
3. Move 2nd data to accumulator.
4. Subtract memory content.
5. Store result.

### FLOWCHART

<img width="578" height="797" alt="image" src="https://github.com/user-attachments/assets/564c3c7a-33ce-4a1c-8920-beb5c24b9b47" />


### Program
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

### Output Table

| MEMORY LOCATION (INPUT)  | MEMORY LOCATION (OUTPUT) |
| -----------------------  | ------------------------ |
|                          |                          |
|      1201:34             |  68:1205                 |
|      1202:12             |  00:1206                 |
|      1203:34             |  c4:1207                 |                            

### Manual Calculations
<img width="1280" height="717" alt="image" src="https://github.com/user-attachments/assets/7624ba80-bc33-4566-9662-1bca9497c45c" />



### OUTPUT SCREEN FROM MASM SOFTWARE
<img width="893" height="587" alt="Screenshot 2025-09-14 182203" src="https://github.com/user-attachments/assets/90edbae7-11ca-4787-a938-8ad347753313" />
<img width="913" height="568" alt="Screenshot 2025-09-14 180909" src="https://github.com/user-attachments/assets/ca69b58d-f24a-4fa4-bf9c-d62735f6effa" />


## 3. MULTIPLICATION

### Algorithm

1. Initialize memory and store operands.
2. Move operands to registers.
3. Multiply.
4. Store result.

### FLOWCHART
<img width="569" height="906" alt="image" src="https://github.com/user-attachments/assets/88be88ff-2896-4a88-b73d-84ccffd2fcf9" />

### Program

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

### Output Table

| MEMORY LOCATION (INPUT) | MEMORY LOCATION (OUTPUT) |
| ----------------------- | ------------------------ |
|                         |                          |
|      1201:34            |   68:1205                |
|      1202:12            |   00:1206                |
|      1203:34            |   c4:1207                |                               

### Manual Calculations
<img width="1280" height="717" alt="image" src="https://github.com/user-attachments/assets/47532648-1875-425d-9d86-ee9a808b205b" />



### OUTPUT SCREEN FROM MASM SOFTWARE
<img width="885" height="587" alt="Screenshot 2025-09-14 182217" src="https://github.com/user-attachments/assets/dd1d9bdf-04c0-455f-b3d1-d15f3a67a645" />
<img width="904" height="566" alt="Screenshot 2025-09-14 183300" src="https://github.com/user-attachments/assets/ba532115-92a6-47d6-b064-c959d2002b31" />


## 4. DIVISION

### Algorithm

1. Load memory location of operands.
2. Perform division.
3. Store result.

### FLOWCHART
<img width="1065" height="802" alt="image" src="https://github.com/user-attachments/assets/25b4a483-0d42-494b-8639-1af3ea17191b" />


### Program
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

### Output Table

| MEMORY LOCATION (INPUT) | MEMORY LOCATION (OUTPUT) |
| ----------------------- | ------------------------ |
|                         |                          |
|     1201:34             |  68:1205                 |
|    1202:12              | 00:1206                  |
|     1203:34             |  c4:1207                 |                                                               

### Manual Calculations
<img width="1280" height="678" alt="image" src="https://github.com/user-attachments/assets/10e0af66-3462-4e2b-98b1-cfc12df355ff" />



### OUTPUT FROM MASM SOFTWARE

<img width="921" height="576" alt="Screenshot 2025-09-14 182238" src="https://github.com/user-attachments/assets/d1b24a8e-d0a9-4486-9686-b860187c5fca" />
<img width="916" height="561" alt="Screenshot 2025-09-14 183450" src="https://github.com/user-attachments/assets/a3c592ae-be5b-4ab7-97f6-abe12a0bbcba" />


## RESULT

Thus, the Assembly Language Programs for 8086 to perform arithmetic operations (Addition, Subtraction, Multiplication, and Division) using both direct and indirect methods were successfully written and executed using MASM.

---
