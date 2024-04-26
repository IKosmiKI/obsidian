### Условный оператор (If-Then)
````
CMP AX, BX
JNS YES #SF=0
NO: #NO выше чем YES
	JMP FIN
YES:
	MOV CX, 1111h
FIN:
````

### Условный оператор (IF-THEN-ELSE)
````
CMP AX, BX
JNS YES #SF=0
NO: #NO выше чем YES
	MOV CX, 2222h
	JMP FIN
YES:
	MOV CX, 1111h
FIN:
````

### Условный оператор (IF-THEN-ELSE-Изоморфный)
**Схема такая же, как выше**
````
CMP AX, BX
JS NO #SF=1
YES:
	MOV CX, 1111h
	JMP FIN
NO:
	MOV CX, 2222h
FIN:
````

### Цикл с постусловием
````
BEG:
	SUB AX, CX
	CMP AX, BX
	JNS BEG
NO:
````


### Цикл с предусловием
````
BEG:
	SUB AX, BX
	JS NO
YES:
	SUB AX, CX
	JMP BEG
NO:
````

### Условный оператор (Краткий формат, составное условие: 2 условия связаны через "И")
**IF(AX>=BX)AND(DX == 7)THEN CX=1111h**
```
CMP AX, BX
JS NO2
YES1:
	CMP DX, 7
	JNZ NO2
YES2:
	MO CX, 1111h
NO2:
NO1:
FIN:
```