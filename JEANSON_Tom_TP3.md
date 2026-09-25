# Compte Rendu TP 3 R1.01
**Tom JEANSON** 
**Groupe :** B2
**N° étudiant :** e22601522

## Exercice 1 - Reprise du TD 3
### Version While
#### Code
```java
/**
* R1.01 - Exercice 1 – Reprise du TD 3
* @author Tom JEANSON
*/
class DecalageDroite{
	void principal(){
		int[] t = {5,7,0,6,10,8,4,1,35,25,8,3};
		System.out.print("Avant\t : ");
		displayTab(t);
		int i = 0;
		int j = t.length - 1;
		int a = 0;
		int b = 0;
		while(i <= j){
			a = t[i];
			b = t[j];
			t[i] = b;
			t[j] = a;
			i++;
			j--;
		}
		System.out.print("Apres\t : ");
		displayTab(t);
	}
	void displayTab(int[] t){
		int i = 0;
		System.out.print("{");
		while(i<t.length-1){
			System.out.print(t[i] + ",");
			i=i+1;
		}
		if(t.length !=0){
			System.out.println(t[i]+"}");
		}else{
			System.out.println("}");
		}
	}
}

```
#### Sortie
```java
Avant	 : {5,7,0,6,10,8,4,1,35,25,8,3}
Apres	 : {3,8,25,35,1,4,8,10,6,0,7,5}


------------------
(program exited with code: 0)
Press return to continue
```
### Version For
#### Code
```java
/**
* R1.01 - Exercice 1 – Reprise du TD 3
* @author Tom JEANSON
*/
class DecalageDroite{
	void principal(){
		int[] t = {10,45,7,12,1,4,46,0,3,5,9,17,4};
		System.out.print("Avant\t : ");
		displayTab(t);
		for(int i = 0, j = t.length -1, a = 0, b = 0; i <= j; i++, j--){
			a = t[i];
			b = t[j];
			t[i] = b;
			t[j] = a;
		}
		System.out.print("Apres\t : ");
		displayTab(t);
	}
	void displayTab(int[] t){
		int i = 0;
		System.out.print("{");
		while(i<t.length-1){
			System.out.print(t[i] + ",");
			i=i+1;
		}
		if(t.length !=0){
			System.out.println(t[i]+"}");
		}else{
			System.out.println("}");
		}
	}
}
```
#### Sortie
```java
Avant	 : {10,45,7,12,1,4,46,0,3,5,9,17,4}
Apres	 : {4,17,9,5,3,0,46,4,1,12,7,45,10}


------------------
(program exited with code: 0)
Press return to continue
```
## Exercice 2 - reprise du TD3
### Version While
#### Code
```java
class Cumul{
	void principal(){
		int[] t = {10,45,7,12,1,4,46,0,3,5,9,17,4};
		System.out.print("t\t : ");
		displayTab(t);
		int i = 1;
		int[] cumul = new int[t.length];
		cumul[0] = t[0];
		while(i < t.length){
			cumul[i] = t[i] + cumul[i-1];
			i++;
		}
		System.out.print("Cumul\t : ");
		displayTab(cumul);
	}
	void displayTab(int[] t){
		int i = 0;
		System.out.print("{");
		while(i<t.length-1){
			System.out.print(t[i] + ",");
			i=i+1;
		}
		if(t.length !=0){
			System.out.println(t[i]+"}");
		}else{
			System.out.println("}");
		}
	}
}
```
#### Sortie
```java
t	 : {10,45,7,12,1,4,46,0,3,5,9,17,4}
Cumul	 : {10,55,62,74,75,79,125,125,128,133,142,159,163}


------------------
(program exited with code: 0)
Press return to continue
```
### Version For
#### Code
```java
class Cumul{
	void principal(){
		int[] t = {0,1,1,2,3,5,8,13,21,34,55,89,136};
		System.out.print("t\t : ");
		displayTab(t);
		int[] cumul = new int[t.length];
		cumul[0] = t[0];
		for(int i = 1; i < t.length; i++) {
			cumul[i] = t[i] + cumul[i-1];
		}
		System.out.print("Cumul\t : ");
		displayTab(cumul);
	}
	void displayTab(int[] t){
		int i = 0;
		System.out.print("{");
		while(i<t.length-1){
			System.out.print(t[i] + ",");
			i=i+1;
		}
		if(t.length !=0){
			System.out.println(t[i]+"}");
		}else{
			System.out.println("}");
		}
	}
}
```
#### Sortie
```java
t	 : {0,1,1,2,3,5,8,13,21,34,55,89,136}
Cumul	 : {0,1,2,4,7,12,20,33,54,88,143,232,368}


------------------
(program exited with code: 0)
Press return to continue
```
## Exercice 3
### 1 Version While
#### Code
```java
/**
* R1.01 - Exercice 3
* @author Tom JEANSON
*/
class Croissant{
	void principal(){
		int[] t = {5,7,0,6,10,12,4,1,35,25,8,3};
		System.out.print("t\t : ");
		displayTab(t);
		int i = 1;
		int biggest = 0;
		int currentLength = 1;
		while(i < t.length && biggest < (t.length - i)){
			if(t[i] >= t[i - 1]) {
				currentLength ++;
			}else{
				if(currentLength > biggest){
					biggest = currentLength;
				}
				currentLength = 1;
			}
			i++;
		}
		System.out.println("Plus grande séquence croissante : " + biggest); 
	}
	void displayTab(int[] t){
		int i = 0;
		System.out.print("{");
		while(i<t.length-1){
			System.out.print(t[i] + ",");
			i=i+1;
		}
		if(t.length !=0){
			System.out.println(t[i]+"}");
		}else{
			System.out.println("}");
		}
	}
}
```
#### Sortie
```java
t	 : {5,7,0,6,10,12,4,1,35,25,8,3}
Plus grande séquence croissante : 4


------------------
(program exited with code: 0)
Press return to continue
```
```java
t	 : {5,0,0,6,10,12,28,35,25,8,3}
Plus grande séquence croissante : 7


------------------
(program exited with code: 0)
Press return to continue
```
### 1 Version For
#### Code
```java
/**
* R1.01 - Exercice 3
* @author Tom JEANSON
*/
class Croissant{
	void principal(){
		int[] t = {5,0,0,6,10,12,28,35,25,8,3};
		System.out.print("t\t : ");
		displayTab(t);
		int biggest = 0;
		for(int i = 1, currentLength = 1; i < t.length && biggest < (t.length - i);	i++){
			if(t[i] >= t[i - 1]) {
				currentLength ++;
			}else{
				if(currentLength > biggest){
					biggest = currentLength;
				}
				currentLength = 1;
			}
		}
		System.out.println("Plus grande séquence croissante : " + biggest); 
	}
	void displayTab(int[] t){
		int i = 0;
		System.out.print("{");
		while(i<t.length-1){
			System.out.print(t[i] + ",");
			i=i+1;
		}
		if(t.length !=0){
			System.out.println(t[i]+"}");
		}else{
			System.out.println("}");
		}
	}
}
```
#### Sortie
```java
t	 : {5,0,0,6,10,12,28,35,25,8,3}
Plus grande séquence croissante : 7


------------------
(program exited with code: 0)
Press return to continue
```
```java
t	 : {5,0,0,6,10,12,28,35,45,45,3,5,6,4}
Plus grande séquence croissante : 9


------------------
(program exited with code: 0)
Press return to continue
```
### 2 Version While
#### Code
```java
/**
* R1.01 - Exercice 3
* @author Tom JEANSON
*/
class Croissant{
	void principal(){
		int[] t = {5,7,0,6,10,8,4,1,35,25,8,3};
		System.out.print("t\t : ");
		displayTab(t);
		int biggest = 0;
		int start = 0;
		int currentStart = 1;
		int end = 0;
		int i = 1;
		int currentLength = 1;
		while(i < t.length && biggest < (t.length - i)){
			if(t[i] >= t[i - 1]) {
				currentLength ++;
			}else{
				if(currentLength > biggest){
					biggest = currentLength;
					start = currentStart;
				}
				currentLength = 1;
				currentStart = i;
			}
			i++;
		}
		end = start + biggest - 1;
		System.out.println("Plus grande séquence croissante : " + biggest);
		System.out.println("Indice de début : " + start);
		System.out.println("Indice de fin : " + end);
	}
	void displayTab(int[] t){
		int i = 0;
		System.out.print("{");
		while(i<t.length-1){
			System.out.print(t[i] + ",");
			i=i+1;
		}
		if(t.length !=0){
			System.out.println(t[i]+"}");
		}else{
			System.out.println("}");
		}
	}
}
```

#### Sortie
```java
t	 : {5,7,0,6,10,8,4,1,35,25,8,3}
Plus grande séquence croissante : 3
Indice de début : 2
Indice de fin : 4


------------------
(program exited with code: 0)
Press return to continue
```
```java
t	 : {}
Plus grande séquence croissante : 0
Indice de début : 0
Indice de fin : -1


------------------
(program exited with code: 0)
Press return to continue
```

### 2 Version For
#### Code
```java
/**
* R1.01 - Exercice 3
* @author Tom JEANSON
*/
class Croissant{
	void principal(){
		int[] t = {5,0,0,6,10,12,28,35,45,45,3,5,6,4};
		System.out.print("t\t : ");
		displayTab(t);
		int biggest = 0;
		int start = 0;
		int currentStart = 1;
		int end = 0;
		for(int i = 1, currentLength = 1; i < t.length && biggest < (t.length - i);	i++){
			if(t[i] >= t[i - 1]) {
				currentLength ++;
			}else{
				if(currentLength > biggest){
					biggest = currentLength;
					start = currentStart;
				}
				currentLength = 1;
				currentStart = i;
			}
		}
		end = start + biggest - 1;
		System.out.println("Plus grande séquence croissante : " + biggest);
		System.out.println("Indice de début : " + start);
		System.out.println("Indice de fin : " + end);
	}
	void displayTab(int[] t){
		int i = 0;
		System.out.print("{");
		while(i<t.length-1){
			System.out.print(t[i] + ",");
			i=i+1;
		}
		if(t.length !=0){
			System.out.println(t[i]+"}");
		}else{
			System.out.println("}");
		}
	}
}
```
#### Sortie
```java
t	 : {5,0,0,6,10,12,28,35,45,45,3,5,6,4}
Plus grande séquence croissante : 9
Indice de début : 1
Indice de fin : 9


------------------
(program exited with code: 0)
Press return to continue
```
```java
t	 : {}
Plus grande séquence croissante : 0
Indice de début : 0
Indice de fin : -1


------------------
(program exited with code: 0)
Press return to continue
```
## Exercice 4
#### Code
```java
/**
* R1.01 - Exercice 4
* @author Tom JEANSON
*/
class TirageAleatoire{
	void principal(){
		int[] t = new int[10];
		for(int i = 0, nbr = 0; i < 1000; i++){
			nbr = (int) (Math.random() * 10);
			t[nbr] = t[nbr] + 1;
		}
		System.out.print("Tirage Aléatoire\t : ");
		displayTab(t);
	}
	void displayTab(int[] t){
		int i = 0;
		System.out.print("{");
		while(i<t.length-1){
			System.out.print(t[i] + ",");
			i=i+1;
		}
		if(t.length !=0){
			System.out.println(t[i]+"}");
		}else{
			System.out.println("}");
		}
	}
}
```
#### Sortie
```java
Tirage Aléatoire	 : {96,99,90,100,88,88,116,106,111,106}


------------------
(program exited with code: 0)
Press return to continue
```
```java
Tirage Aléatoire	 : {104,86,108,100,102,102,93,96,109,100}


------------------
(program exited with code: 0)
Press return to continue
```
```java
Tirage Aléatoire	 : {89,96,102,99,100,94,98,100,106,116}


------------------
(program exited with code: 0)
Press return to continue
```
## Exercice 5 : Conjecture de Syracuse
#### Code
```java
/**
* R1.01 - Exercice 5 : Conjecture de Syracuse
* @author Tom JEANSON
*/
class Syracuse{
	void principal(){
		int nbr = 0;
		int i = 0;
		do{
			nbr = SimpleInput.getInt("Entrer un entier : ");
		}while(nbr <= 0);
		int nbrMax = nbr;
		while(nbr!=1){
			if(nbr%2 == 0){
				nbr = nbr / 2;
			}else{
				nbr = nbr * 3 + 1;
			}
			if(nbr > nbrMax){
				nbrMax = nbr;
			}
			i++;
		}
		System.out.println("Nombre d'itérations : " + i);
		System.out.println("Nombre Max : " + nbrMax);
	}
}
```
#### Sortie
```java
Entrer un entier : 5
Nombre d'itérations : 5
Nombre Max : 16


------------------
(program exited with code: 0)
Press return to continue
```
```java
Entrer un entier : -5
Entrer un entier : 0
Entrer un entier : 1
Nombre d'itérations : 0
Nombre Max : 1


------------------
(program exited with code: 0)
Press return to continue
```
```java
Entrer un entier : 151
Nombre d'itérations : 15
Nombre Max : 1024


------------------
(program exited with code: 0)
Press return to continue
```
## Exercice 6
#### Code
```java
/**
* R1.01 - Exercice 6
* @author Tom JEANSON
*/
class ExerciceSix{
	void principal(){
		int[] t = {5,7,0,6,10,8,4,1,35,25,8,3};
		System.out.print("t\t : ");
		displayTab(t);
		int a = 0;
		int b = 0;
		int i = 0;
		boolean aIsHere = false;
		boolean fini = false;
		a = SimpleInput.getInt("Entrer entier a : ");
		b = SimpleInput.getInt("Entrer entier b : ");
		while(i < t.length && !fini){
			if(aIsHere == false) {
				if(a == t[i]){
					aIsHere = true;
				}
			}else{
				if(b==t[i]){
					fini = true;
				}
			}
			i++;
		}
		if(fini == true){
			System.out.println(a + " et " + b + " sont présents dans la liste dans cet ordre");
		}else{
			System.out.println(a + " et " + b + " ne sont pas présents dans la liste dans cet ordre");
		}
	}
	void displayTab(int[] t){
		int i = 0;
		System.out.print("{");
		while(i<t.length-1){
			System.out.print(t[i] + ",");
			i=i+1;
		}
		if(t.length !=0){
			System.out.println(t[i]+"}");
		}else{
			System.out.println("}");
		}
	}
}
```
#### Sortie
```java
t	 : {5,7,0,6,10,8,4,1,35,25,8,3}
Entrer entier a : 25
Entrer entier b : 8
25 et 8 sont présents dans la liste dans cet ordre


------------------
(program exited with code: 0)
Press return to continue
```
```java
t	 : {}
Entrer entier a : 5
Entrer entier b : 8
5 et 8 ne sont pas présents dans la liste dans cet ordre


------------------
(program exited with code: 0)
Press return to continue
```
```java
t	 : {5,7,0,6,10,8,4,1,35,25,8,3}
Entrer entier a : 5
Entrer entier b : 8
5 et 8 sont présents dans la liste dans cet ordre


------------------
(program exited with code: 0)
Press return to continue
```
```java
t	 : {5,7,0,6,10,8,4,1,35,25,8,3}
Entrer entier a : 8
Entrer entier b : 5
8 et 5 ne sont pas présents dans la liste dans cet ordre


------------------
(program exited with code: 0)
Press return to continue
```
## Exercice 7
#### Code
```java
/**
* R1.01 - Exercice 7
* @author Tom JEANSON
*/
class ExerciceSept{
	void principal(){
		int[] t1 = {5,7,0,6,10,8,4,1,35,25,8,3};
		System.out.print("t1\t : ");
		displayTab(t1);
		int[] t2 = {0,8,4,1,35,2,4};
		System.out.print("t2\t : ");
		displayTab(t2);
		int i = 0;
		int tabAdvanc = 0;
		int[] t3 = new int[t1.length + t2.length];
		while(i < t1.length || i < t2.length){
			if(tabAdvanc < t1.length){
				t3[i] = t1[tabAdvanc];
				i++;
			}
			if(tabAdvanc < t2.length){
				t3[i] = t2[tabAdvanc];
				i++;
			}
			tabAdvanc++;
		}
		System.out.print("t3\t : ");
		displayTab(t3);
	}
	void displayTab(int[] t){
		int i = 0;
		System.out.print("{");
		while(i<t.length-1){
			System.out.print(t[i] + ",");
			i=i+1;
		}
		if(t.length !=0){
			System.out.println(t[i]+"}");
		}else{
			System.out.println("}");
		}
	}
}
```
#### Sortie
```java
t1	 : {5,7,0,6,10,8,4,1,35,25,8,3}
t2	 : {0,8,4,1,35,2,4}
t3	 : {5,0,7,8,0,4,6,1,10,35,8,2,4,4,1,35,25,8,3}


------------------
(program exited with code: 0)
Press return to continue
```
```java
t1	 : {5,7,0,6,10,8,4,1,35,25,8,3}
t2	 : {}
t3	 : {5,7,0,6,10,8,4,1,35,25,8,3}


------------------
(program exited with code: 0)
Press return to continue
```
```java
t1	 : {5,7,0,6,10,8,4,1,35,25,8,3}
t2	 : {4,17,9,5,3,0,46,4,1,12,7,45,10}
t3	 : {5,4,7,17,0,9,6,5,10,3,8,0,4,46,1,4,35,1,25,12,8,7,3,45,10}


------------------
(program exited with code: 0)
Press return to continue
```