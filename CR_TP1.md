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