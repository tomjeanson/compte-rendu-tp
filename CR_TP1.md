## Exercice 4 – Bowling
```java
/**
* Bowling R1.01
* @author Tom JEANSON
*/
class Bowling{
	void principal(){
		int nbrQuilles;
		nbrQuilles = SimpleInput.getInt("Quilles tombées pour la première boule :");
		if (nbrQuilles > 10 || nbrQuilles < 0) {
			System.out.println("Nombre de quilles invalides !");
		} else if (nbrQuilles == 10) {
			System.out.println("Strike !");
		} else if (nbrQuilles < 10) {
			nbrQuilles = nbrQuilles + SimpleInput.getInt("Quilles tombées pour la deuxième boule :");
			if (nbrQuilles > 10 || nbrQuilles < 0) {
				System.out.println("Nombre de quilles invalides !");
			} else if (nbrQuilles == 10) {
				System.out.println("Spare");
			} else
			System.out.println(nbrQuilles +" quilles renversées");
		}
	}
}
```
```java
Quilles tombées pour la première boule :4
Quilles tombées pour la deuxième boule :4
8 quilles renversées

------------------
(program exited with code: 0)
Press return to continue
```
```java
Quilles tombées pour la première boule :10
Strike !


------------------
(program exited with code: 0)
Press return to continue
```
``` java
Quilles tombées pour la première boule :4
Quilles tombées pour la deuxième boule :6
Spare


------------------
(program exited with code: 0)
Press return to continue
```
```java
Quilles tombées pour la première boule :5
Quilles tombées pour la deuxième boule :-10
Nombre de quilles invalides !


------------------
(program exited with code: 0)
Press return to continue
``` 
```java
Quilles tombées pour la première boule :12
Nombre de quilles invalides !


------------------
(program exited with code: 0)
Press return to continue
```