# Compte Rendu TP 1 R1.01
**Tom JEANSON** 
**Groupe :** B2
**N° étudiant :** e22601522
## Exercice 2 – Correction d’erreurs
```java
/**
* Correction d’erreurs R1.01
* @author Tom Jeanson
*/
//erreur de convention : author et * absents
class Syntaxe{ 	 	
	void principal(){
		//erreur de convention, Val2 -> val2 : camelCase
		int val1, val2;
		int val3;
		
		//erreur de syntaxe, ";" manquant
		val1 = SimpleInput.getInt("Premier entier :");
		val2 = SimpleInput.getInt("Deuxieme entier :");
		//erreur de syntaxe, "3" manquant
		val3 = SimpleInput.getInt("Troisieme entier :");
		//erreur de convention, "espace" manquant
		if (val1 < val3 && val2 < val3) {
			//erreur de syntaxe, guillemets non fermés
			System.out.println("Le troisieme entier " + val3 + " est le plus grand.");
		} else if (val1 < val2 && val3 < val2) {
			System.out.println("Le deuxieme entier " + val2 + " est le plus grand.");
		} else if (val2 < val1 && val3 < val1) {
			System.out.println("Le premier entier " + val1 + " est le plus grand.");
		//erreur de syntaxe, "}" manquant
		}	
	}
}
```
#### Exemples 
```java
Premier entier :5
Deuxieme entier :8
Troisieme entier :150
Le troisieme entier 150 est le plus grand.


------------------
(program exited with code: 0)
Press return to continue
```
```java
Premier entier :-20
Deuxieme entier :25
Troisieme entier :1800
Le troisieme entier 1800 est le plus grand.


------------------
(program exited with code: 0)
Press return to continue
```
## Exercice 3 – Premier programme en Java
```java
/**
* Calcul du périmètre et de l'aire d'un cercle R1.01
* @author Tom JEANSON
**/
class CalcCercle{
	void principal(){
		int rayon;
		rayon = SimpleInput.getInt("Rayon du cercle :");
		System.out.println("Périmètre = " + rayon*3.1416*2);
		System.out.println("Aire = " + 3.1416*rayon*rayon);
	}
}
```
#### Exemple
```java
Rayon du cercle :5
Périmètre = 31.416
Aire = 78.54


------------------
(program exited with code: 0)
Press return to continue
```
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
#### Exemples 
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
## Exercice 5 – Fiche de salaire 
```java
/**
* Fiche de salaire R1.01
* @author Tom JEANSON
*/
class FicheSalaire{
	void principal(){
		double salaireBrut, salaireNet, totalPrelevements;
		double assuMaladie, assuVeillesseDeplafonee, assuVeillessePlafonee;
		double fraisPro, csg, crds, chomage;
		salaireBrut = SimpleInput.getDouble("Salaire Brut :");
		assuMaladie = salaireBrut * 0.0075;
		assuVeillesseDeplafonee = salaireBrut * 0.001;
		assuVeillessePlafonee = salaireBrut * 0.0675;
		fraisPro = salaireBrut * 0.0175;
		csg = salaireBrut * 0.075;
		crds = salaireBrut * 0.005;
		chomage = salaireBrut * 0.024;
		totalPrelevements = assuMaladie + assuVeillesseDeplafonee + assuVeillessePlafonee + fraisPro + csg + crds + chomage;
		salaireNet = salaireBrut - totalPrelevements;
		System.out.println("Salaire Brut = " + salaireBrut);
		System.out.println("Détails Prélèvements : ");
		System.out.println("- Assurance maladie = " + assuMaladie);
		System.out.println("- Assurance vieilesse déplafonée = " +  assuVeillesseDeplafonee);
		System.out.println("- Assurance vieilesse plafonée = " + assuVeillessePlafonee);
		System.out.println("- Frais professionels = " + fraisPro);
		System.out.println("- Contribution sociale généralisée = " + csg); 
		System.out.println("- CRDS = " + crds);
		System.out.println("- Chômage = " + chomage);
		System.out.println("- Prélèvements totaux = " + totalPrelevements);
		System.out.println("Salaire Net = " + salaireNet);
	}
}
```
#### Exemple
```java
Salaire Brut :2000
Salaire Brut = 2000.0
Détails Prélèvements : 
- Assurance maladie = 15.0
- Assurance vieilesse déplafonée = 2.0
- Assurance vieilesse plafonée = 135.0
- Frais professionels = 35.0
- Contribution sociale généralisée = 150.0
- CRDS = 10.0
- Chômage = 48.0
- Prélèvements totaux = 395.0
Salaire Net = 1605.0


------------------
(program exited with code: 0)
Press return to continue
```