# SKILL ASSESSMENT 2

### 🎯 **Aim**
To write an assembly language program in 8051 to generate a 250 ms delay using Timer 1 in Mode 1 and blink an LED connected to Port 0.5 continuously.


---

### ⚙️ **Components Required**
- Personal Computer
- Keil µVision Software

---

### 💻 **Program**


```c
ORG 0000H
MAIN: MOV TMOD, #10H
CLR P0.5
AGAIN: MOV TH1, #9EH
MOV TL1, #58H
SETB TR1
WAIT: JNB TF1, WAIT
CLR TR1
CLR TF1
CPL P0.5
SJMP AGAIN
END
```
---
### OUTPUT
<img width="1470" height="1077" alt="Screenshot 2025-10-30 230457" src="https://github.com/user-attachments/assets/3fde855d-94d5-48b8-af99-a1ad8ad9cb8a" />

<img width="1466" height="903" alt="Screenshot 2025-10-30 230625" src="https://github.com/user-attachments/assets/e58ba0d9-f88f-4dfa-9b91-119786dc1652" />


---
### RESULT
Thus a 250 ms delay using Timer 1 in Mode 1 and blink an LED connected to Port 0.5
continuously using 8051 KEIL was done and shown the output.
