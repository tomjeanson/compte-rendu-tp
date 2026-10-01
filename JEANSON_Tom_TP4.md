# Compte Rendu TP 4 R1.01
**Tom JEANSON** 
**Groupe :** B2
**N° étudiant :** e22601522

## Exercice 1 - Reprise du TD
### 1
#### Code
```java
/**
* R1.01 - Exercice 1 – Reprise du TD 3
* @author Tom JEANSON
*/
class CalcCombinaison{
	void principal(){
	
	}
	
	/**
	* calcul de la factorielle du paramètre
	* @param n valeur de la factoriel à calculer, n>=0
	* @return factorielle de n
	*/
	int factorielle (int n){
		int result=1;
		for(int i=1; i <= n; i++){
			result = result * i;
		}
		return result;
	}
	
	/**
	* calcul de la combinaison k parmi n
	* @param n cardinalité de l’ensemble
	* @param k nombre d’éléments dans n avec 0<=k<=n
	* @return nombre de combinaisons de k parmi n
	*/
	int combinaison (int n, int k){
		int result = 0;
		if(n >= k){
			result = factorielle(n)/(factorielle(k)*factorielle(n-k));
		}
		return result;
	}
}
```	
### 2
#### Code
```java
/**
* R1.01 - Exercice 1 – Reprise du TD 3
* @author Tom JEANSON
*/
class CalcCombinaison{
	void principal(){
		testFactorielle();
	}	
	/**
	* calcul de la factorielle du paramètre
	* @param n valeur de la factoriel à calculer, n>=0
	* @return factorielle de n
	*/
	int factorielle (int n){
		int result=1;
		for(int i=1; i <= n; i++){
			result = result * i;
		}
		return result;
	}
	
	/**
	* calcul de la combinaison k parmi n
	* @param n cardinalité de l’ensemble
	* @param k nombre d’éléments dans n avec 0<=k<=n
	* @return nombre de combinaisons de k parmi n
	*/
	int combinaison (int n, int k){
		int result = 0;
		if(n >= k){
			result = factorielle(n)/(factorielle(k)*factorielle(n-k));
		}
		return result;
	}

	/**
	* Teste la méthode factorielle()
	*/
	void testFactorielle () {
		System.out.println ();
		System.out.println ("*** testFactorielle()");
		testCasFactorielle (5, 120);
		testCasFactorielle (0, 1);
		testCasFactorielle (1, 1);
		testCasFactorielle (2, 2);
	}
	
	/**
	* teste un appel de factorielle
	* @param n valeur de la factorielle à calculer
	* @param result resultat attendu
	*/
	void testCasFactorielle (int n, int result) {
		// Affichage
		System.out.print ("factorielle (" + n + ") \t= " + result + "\t : ");
		// Appel
		int resExec = factorielle(n);
		// Verification
		if (resExec == result){
			System.out.println ("OK");
		} else {
			System.err.println ("ERREUR");
		}
	}
}
```
#### Sortie
```java

*** testFactorielle()
factorielle (5) 	= 120	 : OK
factorielle (0) 	= 1	 : OK
factorielle (1) 	= 1	 : OK
factorielle (2) 	= 2	 : OK


------------------
(program exited with code: 0)
Press return to continue
```
### 3
#### Code
```java
/**
* R1.01 - Exercice 1 – Reprise du TD 3
* @author Tom JEANSON
*/
class CalcCombinaison{
	void principal(){
		testFactorielle();
		testCombinaison();
	}	
	/**
	* calcul de la factorielle du paramètre
	* @param n valeur de la factoriel à calculer, n>=0
	* @return factorielle de n
	*/
	int factorielle (int n){
		int result=1;
		for(int i=1; i <= n; i++){
			result = result * i;
		}
		return result;
	}
	
	/**
	* calcul de la combinaison k parmi n
	* @param n cardinalité de l’ensemble
	* @param k nombre d’éléments dans n avec 0<=k<=n
	* @return nombre de combinaisons de k parmi n
	*/
	int combinaison (int n, int k){
		int result = 0;
		if(n >= k){
			result = factorielle(n)/(factorielle(k)*factorielle(n-k));
		}
		return result;
	}

	/**
	* Teste la méthode factorielle()
	*/
	void testFactorielle () {
		System.out.println ();
		System.out.println ("*** testFactorielle()");
		testCasFactorielle (5, 120);
		testCasFactorielle (0, 1);
		testCasFactorielle (1, 1);
		testCasFactorielle (2, 2);
	}
	
	/**
	* teste un appel de factorielle
	* @param n valeur de la factorielle à calculer
	* @param result resultat attendu
	*/
	void testCasFactorielle (int n, int result) {
		// Affichage
		System.out.print ("factorielle (" + n + ") \t= " + result + "\t : ");
		// Appel
		int resExec = factorielle(n);
		// Verification
		if (resExec == result){
			System.out.println ("OK");
		} else {
			System.err.println ("ERREUR");
		}
	}

	/**
	* Teste la méthode combinaison()
	*/
	void testCombinaison(){
		System.out.println ();
		System.out.println ("*** testCombinaison()");
		testCasCombinaison (10,5,252);
		testCasCombinaison (5,2,10);
		testCasCombinaison (4,4,1);
		testCasCombinaison (8,6,28);
	}
	
	/**
	* teste un appel de factorielle
	* @param n cardinalité de l’ensemble
	* @param k nombre d’éléments dans n avec 0<=k<=n
	* @param result resultat attendu
	*/
	
	void testCasCombinaison (int n, int k, int result){
		//Affichage
		System.out.print ("combinaison(" + n + ", " + k + ") \t= " + result + "\t : ");
		// Appel
		int resExec = combinaison(n,k);
		if (resExec == result){
			System.out.println ("OK");
		} else {
			System.err.println ("ERREUR");
		}
	}
}
```
#### Sortie
```java
*** testFactorielle()
factorielle (5) 	= 120	 : OK
factorielle (0) 	= 1	 : OK
factorielle (1) 	= 1	 : OK
factorielle (2) 	= 2	 : OK

*** testCombinaison()
combinaison(10, 5) 	= 252	 : OK
combinaison(5, 2) 	= 10	 : OK
combinaison(4, 4) 	= 1	 : OK
combinaison(8, 6) 	= 28	 : OK


------------------
(program exited with code: 0)
Press return to continue
```
## Exercice 2
### 1.
#### Code
```java
/**
* R1.01 - Exercice 2
* @author Tom JEANSON
*/
class Divisibilite{
	void principal(){
		System.out.println(estDiviseur(10,5));
		System.out.println(estDiviseur(20,3));
	}
	
	/**
	* teste la divisibilité de deux entiers
	* @param p entier positif à tester pour la divisibilité
	* @param q diviseur strictement positif
	* @return vrai ssi q divise p
	*/
	boolean estDiviseur (int p, int q){
		boolean diviseur = false;
		if(p%q == 0){
			diviseur = true;
		}
		return diviseur;
	}	
}
```
#### Sortie
```java
true
false


------------------
(program exited with code: 0)
Press return to continue
```
### 2.
#### Code
```java
/**
* R1.01 - Exercice 2
* @author Tom JEANSON
*/
class Divisibilite{
	void principal(){
		testEstDiviseur();
	}
	
	/**
	* teste la divisibilité de deux entiers
	* @param p entier positif à tester pour la divisibilité
	* @param q diviseur strictement positif
	* @return vrai ssi q divise p
	*/
	boolean estDiviseur (int p, int q){
		boolean diviseur = false;
		if(p%q == 0){
			diviseur = true;
		}
		return diviseur;
	}
	
	/**
	* Teste la méthode estDiviseur()
	*/
	void testEstDiviseur(){
		System.out.println ();
		System.out.println ("*** testDiviseur()");
		testCasEstDiviseur(4,3,false);
		testCasEstDiviseur(15,5,true);
		testCasEstDiviseur(12,4,true);
		testCasEstDiviseur(10,10,true);
		testCasEstDiviseur(120,11,false);
	}

	/**
	 * Teste un appel de la méthode estDiviseur()
	* @param p entier positif à tester pour la divisibilité
	* @param q diviseur strictement positif
	* @param result resultat attendu
	*/
	void testCasEstDiviseur(int p, int q, boolean result){
		// Affichage
		System.out.print("estDivisible (" + p + ", " + q + ") \t= " + result + "\t : ");
		
		// Appel
		boolean resExec = estDiviseur(p,q);
		
		// Verification
		if (resExec == result){
			System.out.println ("OK");
		} else {
			System.err.println ("ERREUR");
		}
	}
}
```
#### Sortie
```java
*** testDiviseur()
estDivisible (4, 3) 	= false	 : OK
estDivisible (15, 5) 	= true	 : OK
estDivisible (12, 4) 	= true	 : OK
estDivisible (10, 10) 	= true	 : OK
estDivisible (120, 11) 	= false	 : OK


------------------
(program exited with code: 0)
Press return to continue	
```
## Exercice 3 - Nombre parfait
### 1.
Je n'ai pas remis le test de estDiviseur car déjà fait dans l'exercice d'avant.
#### Code
```java

```
#### Sortie
```java

```