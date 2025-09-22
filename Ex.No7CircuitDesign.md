# Ex.No: 7  Logic Programming –  Logic Circuit Design
### DATE: 12.09.2025
### REGISTER NUMBER : 212223060110
### AIM: 
To write a logic program to design a circuit like half adder and half subtractor.
###  Algorithm:
1. Start the Program
2. Design a AND gate logic if both inputs are 1 then output is 1.
3. Design a OR gate logic if any one of input is 1 then output is 1.
4. Design a XOR gate logic if both inputs are different then output is 1.
5. Design a NOT gate logic if input is 0 then output is 1.
6. Design a half adder and half subtractor using the rules.
7. Test the logic.
8. Stop the program.

### Program:

```
halfadder(X,Y,Sum,Carry):-
xor(X,Y,Sum),
and(X,Y,Carry).
halfsub(X,Y,Diff,Borrow):-
	xor(X,Y,Diff),
	not(X,Z),
	and(X,Y,Borrow).
fulladd(X,Y,Z,Sum,Carry):- 
	xor(X,Y,A),
	xor(A,Z,Sum),
	and(A,Z,B),
	and(X,Y,C),
	or(B,C,Carry).
xor(0,0,0).
xor(0,1,1).
xor(1,0,1).
xor(1,1,0).
and(0,0,0).
and(0,1,0).
and(1,0,0).
and(1,1,1).
or(0,1,1).
or(0,0,0).
or(1,0,1).
or(1,1,1).
not(0,1).
not(1,0).

```

### Output:

<img width="452" height="161" alt="image" src="https://github.com/user-attachments/assets/7c4b5cc0-fbe7-4c4c-ba5b-f3574788e2b7" />

<img width="937" height="166" alt="image" src="https://github.com/user-attachments/assets/9754e122-4f85-4e7a-b3d3-de710e3028da" />

<img width="934" height="184" alt="image" src="https://github.com/user-attachments/assets/5dfc3255-ad13-403a-a9f7-4ce818eca91e" />






### Result:
Thus the truth table of circuit verified sucessfully.
