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
##Exercice 3
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