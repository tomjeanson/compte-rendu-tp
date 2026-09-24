# Compte Rendu TP 2 R1.01
**Tom JEANSON** 
**Groupe :** B2
**N° étudiant :** e22601522

## Exercice 1 – Reprise du TD 2
### 1.
#### Code (avec while)
```java
/**
* R1.01 - Exercice 1 – Reprise du TD 2
* @author Tom JEANSON
*/
class Nombre {
	void principal() {
		int nbr;
		nbr = 0;
		while(nbr != -1) {
			nbr = SimpleInput.getInt("Entrer un nombre :");
			System.out.println(nbr);
		}
	}
}

```
#### Sortie
```java
Entrer un nombre :5
5
Entrer un nombre :1
1
Entrer un nombre :1
1
Entrer un nombre :0
0
Entrer un nombre :-1
-1


------------------
(program exited with code: 0)
Press return to continue
```
#### Code (avec do while)
```java
/**
* R1.01 - Exercice 1 – Reprise du TD 2
* @author Tom JEANSON
*/
class Nombre {
	void principal() {
		int nbr;
		do {
			nbr = SimpleInput.getInt("Entrer un nombre :");
			System.out.println(nbr);
		} while(nbr != -1);
	}
}
```
#### Sortie
```java
Entrer un nombre :5
5
Entrer un nombre :4
4
Entrer un nombre :3
3
Entrer un nombre :9
9
Entrer un nombre :-1
-1


------------------
(program exited with code: 0)
Press return to continue
```
### 2.
#### Code
```java
/**
* R1.01 - Exercice 1 – Reprise du TD 2
* @author Tom JEANSON
*/
class Nombre {
	void principal() {
		int nbr, i, total;
		nbr = 0;
		i = 0;
		total = 0;
		while(nbr != -1) {
			i += 1;
			nbr = SimpleInput.getInt("Entrer un nombre : ");
			total = total + nbr;
			if(nbr != -1) {
				System.out.println("Moyenne des nombres saisis = " + total / i);
			}
		}
	}
}

```
#### Sortie
```java
Entrer un nombre : 12
Moyenne des nombres saisis = 12
Entrer un nombre : 8      
Moyenne des nombres saisis = 10
Entrer un nombre : -12     
Moyenne des nombres saisis = 2
Entrer un nombre : 29
Moyenne des nombres saisis = 9
Entrer un nombre : -1


------------------
(program exited with code: 0)
Press return to continue
```
## Exercice 2 – Programme mystère
### 1.
#### Exécutions qui se terminent
```java
Première valeur : 24
Deuxième valeur : 6
Le résultat est : 6


------------------
(program exited with code: 0)
Press return to continue
```
#### Exécutions qui ne se terminent pas
```java
Première valeur : 3
Deuxième valeur : 0
```
#### Rôle du programme
Le rôle du programme est de trouvé le PGCD de deux nombres et de l'afficher.
### 2.
#### Code (version while)
```java
/**
* Rôle à deviner
* @author M.Adam
*/
class ADeviner {
	void principal() {
		int val1;
		int val2;
		val1 = 0;
		val2 = 0;
		while(val1 <= 0 || val2 <= 0) {
			val1 = SimpleInput.getInt ("Première valeur : ");
			val2 = SimpleInput.getInt ("Deuxième valeur : ");
		}
		while (val1 != val2) {
			if (val1 > val2) {
				val1 = val1 - val2;
			} else {
				val2 = val2 - val1;
			}
		}
		System.out.println("Le résultat est : " + val1);
	}
}
```
#### Sortie
```java
Première valeur : 0
Deuxième valeur : 4
Première valeur : 54
Deuxième valeur : -10
Première valeur : 12
Deuxième valeur : 78
Le résultat est : 6


------------------
(program exited with code: 0)
Press return to continue
```
#### Code (version do while)
```java
/**
* Rôle à deviner
* @author M.Adam
*/
class ADeviner {
	void principal() {
		int val1;
		int val2;
		do {
			val1 = SimpleInput.getInt ("Première valeur : ");
			val2 = SimpleInput.getInt ("Deuxième valeur : ");
		} while(val1 <= 0 || val2 <= 0);
		while (val1 != val2) {
			if (val1 > val2) {
				val1 = val1 - val2;
			} else {
				val2 = val2 - val1;
			}
		}
		System.out.println("Le résultat est : " + val1);
	}
}

```
#### Sortie
```java
Première valeur : -24
Deuxième valeur : 4      
Première valeur : 12
Deuxième valeur : 0
Première valeur : -25
Deuxième valeur : -48
Première valeur : 12
Deuxième valeur : 79
Le résultat est : 1


------------------
(program exited with code: 0)
Press return to continue
```
## Exercice 3 – Nombre croissant
#### Code
```java
/**
* R1.01 - Exercice 3 – Nombre croissant
* @author Tom JEANSON
*/
class NbrCroissant{
	void principal(){
		int nbr1, nbr2;
		nbr1 = SimpleInput.getInt("Entrer un nombre : ");
		nbr2 = nbr1;
		while(nbr1 >= nbr2) {
			nbr2 = nbr1;
			nbr1 = SimpleInput.getInt("Entrer un nombre : ");
		}	
	}
}

```	
#### Sortie
```java
Entrer un nombre : 10
Entrer un nombre : 20
Entrer un nombre : 10


------------------
(program exited with code: 0)
Press return to continue
```
## Exercice 4 – Distributeur automatique
#### Code
```java
/**
* R1.01 - Exercice 4 – Distributeur automatique
* @author Tom JEANSON
*/
class Distributeur{
	void principal(){
		int prix, montant, rendu, resteRendu;
		int billet50, billet20, billet10, billet5;
		int piece2, piece1;
		prix = SimpleInput.getInt("Entrer le prix : ");
		montant = SimpleInput.getInt("Entrer le montant entré dans la machine : ");
		while (prix > montant) {
			montant = montant + SimpleInput.getInt("Montant insuffisant ! Ajouter un montant :");
		}
		if (prix == montant) {
			System.out.println("Produit acheté");
			System.out.println("Pas de rendu de monnaie");
		} else {
			rendu = montant - prix;
			billet50 = rendu / 50;
			resteRendu = rendu - billet50 * 50;
			billet20 = resteRendu / 20;
			resteRendu = resteRendu - billet20 * 20;
			billet10 = resteRendu / 10;
			resteRendu = resteRendu - billet10 * 10;
			billet5 = resteRendu / 5;
			resteRendu = resteRendu - billet5 * 5;
			piece2 = resteRendu / 2;
			resteRendu = resteRendu - piece2 * 2;
			piece1 = resteRendu;
			System.out.println("Rendu monnaie de :" + rendu);
			System.out.println(billet50 + " Billet(s) de 50, " + billet20 + " Billet(s) de 20, " + billet10 + " Billet(s) de 10, " + billet5 + " Billet(s) de 5, " + piece2 + " Piece(s) de 2, " + piece1 + " Piece de 1");
		}
	}
}
```
#### Sortie
```java
Entrer le prix : 45
Entrer le montant entré dans la machine : 2
Montant insuffisant ! Ajouter un montant :7
Montant insuffisant ! Ajouter un montant :15
Montant insuffisant ! Ajouter un montant :34
Rendu monnaie de :13
0 Billet(s) de 50, 0 Billet(s) de 20, 1 Billet(s) de 10, 0 Billet(s) de 5, 1 Piece(s) de 2, 1 Piece de 1


------------------
(program exited with code: 0)
Press return to continue
```
```java
Entrer le prix : 46
Entrer le montant entré dans la machine : 46
Produit acheté
Pas de rendu de monnaie


------------------
(program exited with code: 0)
Press return to continue
```
```java
Entrer le prix : 14
Entrer le montant entré dans la machine : 35
Rendu monnaie de :21
0 Billet(s) de 50, 1 Billet(s) de 20, 0 Billet(s) de 10, 0 Billet(s) de 5, 0 Piece(s) de 2, 1 Piece de 1


------------------
(program exited with code: 0)
Press return to continue
```
## Exercice 5 – Devine le nombre...
#### Code
```java
/**
* R1.01 - Exercice 5 – Devine le nombre...
* @author Tom JEANSON
*/
class DevineNombre {
	void principal() {
		int nbrUser, i;
		i = 0;
		int nbrMystere = (int) (Math.random() * 100);
		do {
			nbrUser = SimpleInput.getInt("Entrer un nombre : ");
			i = i + 1;
			if (nbrUser > nbrMystere) {
				System.out.println("Trop grand !");
			} else if (nbrUser < nbrMystere) {
				System.out.println("Trop petit !");
			}
		} while(nbrUser != nbrMystere);
		System.out.println("Nombre trouvé en " + i + " itération(s)");
	}
}

```
#### Sortie
```java
Entrer un nombre : 1
Trop petit !
Entrer un nombre : 5
Trop petit !
Entrer un nombre : 45
Trop petit !
Entrer un nombre : 85
Trop grand !
Entrer un nombre : 60
Trop grand !
Entrer un nombre : 50
Trop grand !
Entrer un nombre : 47
Nombre trouvé en 7 itération(s)


------------------
(program exited with code: 0)
Press return to continue
```
## Exercice 6 – Fais deviner un nombre...
#### Code
```java
/**
* R1.01 - Exercice 6 – Fais deviner un nombre...
* @author Tom JEANSON
*/
class TrouveNombre {
	void principal() {
			int nbr, a, b;
			char diff;
			boolean sucess;
			sucess = false;
			a = 0;
			b = 1000;
			System.out.println("Pensez à un nombre entre 0 et 1000");
			do {
				nbr = (b - a) / 2 + a;
				System.out.println("Le nombre auquel vous pensez est-il : " + nbr + " ?");
				diff = SimpleInput.getChar("Si c'est le bon nombre, entrez : = ; Si c'est supérieur à votre nombre, entrez : - ; si c'est inférieur à votre nombre, entrez : + ");
				if (diff == '=') {
					System.out.println("Nombre trouvé !");
					sucess = true;
				} else if (diff == '-') {
					b = nbr;
				} else if (diff == '+') {
					a = nbr;
				}else {
					System.out.println("Valeur incorrect");
				}
			} while (sucess == false);
	}
}
```
#### Sortie
*Je prends 72 comme valeur :*
```java
Pensez à un nombre entre 0 et 1000
Le nombre auquel vous pensez est-il : 500 ?
Si c'est le bon nombre, entrez : = ; Si c'est supérieur à votre nombre, entrez : - ; si c'est inférieur à votre nombre, entrez : + -
Le nombre auquel vous pensez est-il : 250 ?
Si c'est le bon nombre, entrez : = ; Si c'est supérieur à votre nombre, entrez : - ; si c'est inférieur à votre nombre, entrez : + -
Le nombre auquel vous pensez est-il : 125 ?
Si c'est le bon nombre, entrez : = ; Si c'est supérieur à votre nombre, entrez : - ; si c'est inférieur à votre nombre, entrez : + -
Le nombre auquel vous pensez est-il : 62 ?
Si c'est le bon nombre, entrez : = ; Si c'est supérieur à votre nombre, entrez : - ; si c'est inférieur à votre nombre, entrez : + +
Le nombre auquel vous pensez est-il : 93 ?
Si c'est le bon nombre, entrez : = ; Si c'est supérieur à votre nombre, entrez : - ; si c'est inférieur à votre nombre, entrez : + -
Le nombre auquel vous pensez est-il : 77 ?
Si c'est le bon nombre, entrez : = ; Si c'est supérieur à votre nombre, entrez : - ; si c'est inférieur à votre nombre, entrez : + -
Le nombre auquel vous pensez est-il : 69 ?
Si c'est le bon nombre, entrez : = ; Si c'est supérieur à votre nombre, entrez : - ; si c'est inférieur à votre nombre, entrez : + +
Le nombre auquel vous pensez est-il : 73 ?
Si c'est le bon nombre, entrez : = ; Si c'est supérieur à votre nombre, entrez : - ; si c'est inférieur à votre nombre, entrez : + -
Le nombre auquel vous pensez est-il : 71 ?
Si c'est le bon nombre, entrez : = ; Si c'est supérieur à votre nombre, entrez : - ; si c'est inférieur à votre nombre, entrez : + +
Le nombre auquel vous pensez est-il : 72 ?
Si c'est le bon nombre, entrez : = ; Si c'est supérieur à votre nombre, entrez : - ; si c'est inférieur à votre nombre, entrez : + =
Nombre trouvé !


------------------
(program exited with code: 0)
Press return to continue

```
*Je prends 932 comme valeur :*
```java
Pensez à un nombre entre 0 et 1000
Le nombre auquel vous pensez est-il : 500 ?
Si c'est le bon nombre, entrez : = ; Si c'est supérieur à votre nombre, entrez : - ; si c'est inférieur à votre nombre, entrez : + +
Le nombre auquel vous pensez est-il : 750 ?
Si c'est le bon nombre, entrez : = ; Si c'est supérieur à votre nombre, entrez : - ; si c'est inférieur à votre nombre, entrez : + +
Le nombre auquel vous pensez est-il : 875 ?
Si c'est le bon nombre, entrez : = ; Si c'est supérieur à votre nombre, entrez : - ; si c'est inférieur à votre nombre, entrez : + +
Le nombre auquel vous pensez est-il : 937 ?
Si c'est le bon nombre, entrez : = ; Si c'est supérieur à votre nombre, entrez : - ; si c'est inférieur à votre nombre, entrez : + -
Le nombre auquel vous pensez est-il : 906 ?
Si c'est le bon nombre, entrez : = ; Si c'est supérieur à votre nombre, entrez : - ; si c'est inférieur à votre nombre, entrez : + +
Le nombre auquel vous pensez est-il : 921 ?
Si c'est le bon nombre, entrez : = ; Si c'est supérieur à votre nombre, entrez : - ; si c'est inférieur à votre nombre, entrez : + +
Le nombre auquel vous pensez est-il : 929 ?
Si c'est le bon nombre, entrez : = ; Si c'est supérieur à votre nombre, entrez : - ; si c'est inférieur à votre nombre, entrez : + +
Le nombre auquel vous pensez est-il : 933 ?
Si c'est le bon nombre, entrez : = ; Si c'est supérieur à votre nombre, entrez : - ; si c'est inférieur à votre nombre, entrez : + -
Le nombre auquel vous pensez est-il : 931 ?
Si c'est le bon nombre, entrez : = ; Si c'est supérieur à votre nombre, entrez : - ; si c'est inférieur à votre nombre, entrez : + +
Le nombre auquel vous pensez est-il : 932 ?
Si c'est le bon nombre, entrez : = ; Si c'est supérieur à votre nombre, entrez : - ; si c'est inférieur à votre nombre, entrez : + =
Nombre trouvé !


------------------
(program exited with code: 0)
Press return to continue
```
## Exercice 7 – Projet Euler : Problème 1
#### Code
```java
/**
* R1.01 - Exercice 7 – Projet Euler : Problème 1
* @author Tom JEANSON
*/
class ProjetEuler {
	void principal() {
		int i, nbr;
		i = 0;
		nbr = 0;
		System.out.println("Multiples de 3 et 5 :");
		while(i < 1000) {
			if(i%3 == 0 || i%5 == 0) {
				nbr = nbr + i;
			}
			i = i + 1;
		}
		System.out.println(nbr);
	}
}
```
#### Sortie
```java
Multiples de 3 et 5 :
233168


------------------
(program exited with code: 0)
Press return to continue
```