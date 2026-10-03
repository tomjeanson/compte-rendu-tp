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
/**
* R1.01 - Exercice 3 – Nombre parfait
* @author Tom JEANSON
*/
class NombreParfait{
	void principal(){
		System.out.println("6 est un nombre parfait renvoie : " + estParfait(6));
		System.out.println("8 est un nombre parfait renvoie : " + estParfait(8));
	}
	
	/**
	* teste si un nombre est parfait
	* @param a entier positif
	* @return vrai ssi a est un nombre parfait
	*/
	boolean estParfait (int a) {
		int sommeDiviseur = 0;
		int i = 1;
		boolean result = false;
		while(i < a && sommeDiviseur <= a){
			if(estDiviseur(a,i) == true){
				sommeDiviseur = sommeDiviseur + i;
			}
			i++;
		}
		if(sommeDiviseur == a){
			result = true;
		}
		return result;
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
6 est un nombre parfait renvoie : true
8 est un nombre parfait renvoie : false


------------------
(program exited with code: 0)
Press return to continue
```
### 2.
#### Code
```java
/**
* R1.01 - Exercice 3 – Nombre parfait
* @author Tom JEANSON
*/
class NombreParfait{
	void principal(){
		testEstParfait();
	}
	
	/**
	* teste si un nombre est parfait
	* @param a entier positif
	* @return vrai ssi a est un nombre parfait
	*/
	boolean estParfait (int a) {
		int sommeDiviseur = 0;
		int i = 1;
		boolean result = false;
		while(i < a && sommeDiviseur <= a){
			if(estDiviseur(a,i) == true){
				sommeDiviseur = sommeDiviseur + i;
			}
			i++;
		}
		if(sommeDiviseur == a){
			result = true;
		}
		return result;
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
	 * Teste la méthode estParfait	
	 */
	void testEstParfait(){
		System.out.println ();
		System.out.println ("*** testEstParfait()");
		testCasEstParfait(6, true);
		testCasEstParfait(10, false);
		testCasEstParfait(28, true);
		testCasEstParfait(35, false);
		testCasEstParfait(496, true);
	}
	
	/**
	 * Teste un appel de estParfait
	 * @param nombre a verifier
	 * @param resultat attendu
	 */
	void testCasEstParfait(int a, boolean result){
		// Affichage
		System.out.print ("estParfait (" + a + ") \t= " + result + "\t : ");
		
		// Appel
		boolean resExec = estParfait(a);
		
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
*** testEstParfait()
estParfait (6) 	= true	 : OK
estParfait (10) 	= false	 : OK
estParfait (28) 	= true	 : OK
estParfait (35) 	= false	 : OK
estParfait (496) 	= true	 : OK


------------------
(program exited with code: 0)
Press return to continue
```
### 3.
J'ai amélioré légérement le code de estParfait en allant que jusqu'à n/2 d'un nombre n calculé car il est evident que tout ce qui sera superieur a n/2 ne sera pas diviseur de n à part n lui même qu'on ne compte pas dans estParfait. De plus j'ai ajouté un test pour 1 qui marche effectivement. Il y a un léger problème d'affichage avec les tab dans les tests d'execution que je ne sais pas vraiment géré néanmoins.
#### Code
```java
/**
* R1.01 - Exercice 3 – Nombre parfait
* @author Tom JEANSON
*/
class NombreParfait{
	void principal(){
		testEstParfait();
		QuatreNbParfaits();
	}
		
	/**
	* teste si un nombre est parfait
	* @param a entier positif
	* @return vrai ssi a est un nombre parfait
	*/
	boolean estParfait (int a) {
		int sommeDiviseur = 0;
		int i = 1;
		boolean result = false;
		while(i <= (a/2) && sommeDiviseur <= a){
			if(estDiviseur(a,i) == true){
				sommeDiviseur = sommeDiviseur + i;
			}
			i++;
		}
		if(sommeDiviseur == a){
			result = true;
		}
		return result;
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
	* Teste la méthode estParfait	
	*/
	void testEstParfait(){
		System.out.println ();
		System.out.println ("*** testEstParfait()");
		testCasEstParfait(1, false);
		testCasEstParfait(6, true);
		testCasEstParfait(10, false);
		testCasEstParfait(28, true);
		testCasEstParfait(35, false);
		testCasEstParfait(496, true);
	}
		
	/**
	* Teste un appel de estParfait
	* @param nombre a verifier
	* @param resultat attendu
	*/
	void testCasEstParfait(int a, boolean result){
		// Affichage
		System.out.print ("estParfait (" + a + ") \t= " + result + "\t : ");
			
		// Appel
		boolean resExec = estParfait(a);
			
		// Verification
		if (resExec == result){
		System.out.println ("OK");
		} else {
		System.err.println ("ERREUR");
		}
	}
		
	/**
	* Affiche les quatre premiers nombres parfaits
	*/
	void QuatreNbParfaits(){
		System.out.println("Les quatres premiers nombres parfaits sont : ");
		for(int i = 1, totalParfaits = 0; totalParfaits < 4; i++){
			if(estParfait(i) == true){
				totalParfaits ++;
				System.out.println("- " + i);
			}
		}
	}
}

```
#### Sortie
```java
*** testEstParfait()
estParfait (1) 	= false	 : OK
estParfait (6) 	= true	 : OK
estParfait (10) 	= false	 : OK
estParfait (28) 	= true	 : OK
estParfait (35) 	= false	 : OK
estParfait (496) 	= true	 : OK
Les quatres premiers nombres parfaits sont : 
- 6
- 28
- 496
- 8128


------------------
(program exited with code: 0)
Press return to continue
```
## Exercice 4 - Ordre croissant
### 1.
J'ai réutilisé la méthode displayTab du TP précédent afin d'afficher dans le terminal les tableaux pour les tests.
#### Code
```java
/**
* R1.01 - Exercice 4 - Ordre croissant
* @author Tom JEANSON
*/
class OrdreCroissant{
	void principal(){
		testEstCroissant();
	}
	
	/**
	* teste si les valeurs d’un tableau sont triées par ordre croissant
	* @param t tableau d’entiers
	* @return vrai ssi les valeurs du tableau sont en ordre croissant
	*/
	boolean estCroissant (int[] t){
		return true;
		}

	/**
	 * Teste la méthode estCroissant
	 */
	void testEstCroissant(){
		System.out.println ();
		System.out.println ("*** testEstCroissant()");
		testCasEstCroissant(new int[]{1,2,3,4,4},true);
		testCasEstCroissant(new int[]{-10,-5,0,12,45},true);
		testCasEstCroissant(new int[]{4,5,8,12,11,15},false);
		testCasEstCroissant(new int[]{1},true);
	}

	/**
	 * Teste la méthode estCroissant
	 * @param tableau d'entiers à verifier
	 * @param resultat attendu
	 */
	void testCasEstCroissant(int[] t, boolean result){
		//Affichage
		System.out.print("estCroissant(");
		displayTab(t);
		System.out.print(") \t= " + result + "\t : ");
		
		//Appel
		boolean resExec = estCroissant(t);
		
		//Verification
		if (resExec == result){
		System.out.println ("OK");
		} else {
		System.err.println ("ERREUR");
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
			System.out.print(t[i]+"}");
		}else{
			System.out.print("}");
		}
	}
}
```
#### Sortie
Nécessairement fausse car estCroissant renvoie toujours true afin que le programme s'éxecute.	
```java
*** testEstCroissant()
estCroissant({1,2,3,4,4}) 	= true	 : OK
estCroissant({-10,-5,0,12,45}) 	= true	 : OK
estCroissant({4,5,8,12,11,15}) 	= false	 : ERREUR
estCroissant({1}) 	= true	 : OK


------------------
(program exited with code: 0)
Press return to continue
```	
### 2.
#### Code
```java
/**
* R1.01 - Exercice 4 - Ordre croissant
* @author Tom JEANSON
*/
class OrdreCroissant{
	void principal(){
		testEstCroissant();
	}
	
	/**
		 teste si les valeurs d’un tableau sont triées par ordre croissant
	* @param t tableau d’entiers
	* @return vrai ssi les valeurs du tableau sont en ordre croissant
	*/
	boolean estCroissant (int[] t){
		boolean result = true;
		for(int i = 0; i < t.length - 1 && result == true; i++){
			if(t[i] > t[i+1]){
				result = false;
			}
		}
		return result;
	}
	
	/**
	 * Teste la méthode estCroissant
	 */
	void testEstCroissant(){
		System.out.println ();
		System.out.println ("*** testEstCroissant()");
		int[] a = {1,2,3,4,4};
		testCasEstCroissant(a,true);
		testCasEstCroissant(a = new int[] {-10,-5,0,12,45},true);
		testCasEstCroissant(a = new int[]{4,5,8,12,11,15},false);
		testCasEstCroissant(a = new int[]{1},true);
		testCasEstCroissant(a = new int[]{6,2},false);
	}

	/**
	 * Teste la méthode estCroissant
	 * @param tableau d'entiers à verifier
	 * @param resultat attendu
	 */
	void testCasEstCroissant(int[] t, boolean result){
		//Affichage
		System.out.print("estCroissant(");
		displayTab(t);
		System.out.print(") \t= " + result + "\t : ");
		
		//Appel
		boolean resExec = estCroissant(t);
		
		//Verification
		if (resExec == result){
		System.out.println ("OK");
		} else {
		System.err.println ("ERREUR");
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
			System.out.print(t[i]+"}");
		}else{
			System.out.print("}");
		}
	}
}
```
#### Sortie
```java
*** testEstCroissant()
estCroissant({1,2,3,4,4}) 	= true	 : OK
estCroissant({-10,-5,0,12,45}) 	= true	 : OK
estCroissant({4,5,8,12,11,15}) 	= false	 : OK
estCroissant({1}) 	= true	 : OK
estCroissant({6,2}) 	= false	 : OK


------------------
(program exited with code: 0)
Press return to continue
```
## Exercice 5 - Nombres d'occurrences
### 1.
#### Code
```java
/**
* R1.01 -Exercice 5 - Nombres d'occurrences
* @author Tom JEANSON
*/
class NbOccurences{
	void principal(){
		String a = "texte pour test";
		char b = 't';
		System.out.println("Nombre de " + b + " dans la chaine de caractère : \t" + a + " = \t" + nbOcc(a,b));
	}
	
	/**
	* cherche combien de fois un caractère est présent dans une chaîne de caractères
	* @param chaine Chaine de caractère
	* @param car Caractere a rechercher
	* @return nombre d’occurences de car dans chaine
	*/
	int nbOcc (String chaine, char c){
		int result = 0;
		for(int i = 0; i < chaine.length() ; i++){
			if(chaine.charAt(i) == c){
				result ++;
			}
		}
		return result;
	}
}
```
#### Sortie
```java
Nombre de t dans la chaine de caractère : 	texte pour test = 	4


------------------
(program exited with code: 0)
Press return to continue

```
### 2.
#### Code
```java
/**
* R1.01 -Exercice 5 - Nombres d'occurrences
* @author Tom JEANSON
*/
class NbOccurences{
	void principal(){
		testNbOcc();
	}
	
	/**
	* cherche combien de fois un caractère est présent dans une chaîne de caractères
	* @param chaine Chaine de caractère
	* @param car Caractere a rechercher
	* @return nombre d’occurences de car dans chaine
	*/
	int nbOcc (String chaine, char c){
		int result = 0;
		for(int i = 0; i < chaine.length() ; i++){
			if(chaine.charAt(i) == c){
				result ++;
			}
		}
		return result;
	}
	/**
	* Teste la méthode NbOcc
	*/
	void testNbOcc(){
		System.out.println ();
		System.out.println ("*** testNbOcc()");
		testCasNbOcc("bonjour",'z',0);
		testCasNbOcc("eternel",'e',3);
		testCasNbOcc("aller au restaurant",'u',2);
		testCasNbOcc("aller au restaurant",'a',4);
	}
	
	/**
	* Teste
	* @param chaine Chaine de caractère
	* @param car Caractere a rechercher
	* @return nombre d’occurences de car dans chaine
	*/
	void testCasNbOcc(String chaine, char c, int result){
		//Affichage
		System.out.print("NbOcc(" + chaine + ", " + c + ") \t= " + result + "\t : ");
		
		//Appel
		int resExec = nbOcc(chaine, c);
		
		//Verification
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
*** testNbOcc()
NbOcc(bonjour, z) 	= 0	 : OK
NbOcc(eternel, e) 	= 3	 : OK
NbOcc(aller au restaurant, u) 	= 2	 : OK
NbOcc(aller au restaurant, a) 	= 4	 : OK


------------------
(program exited with code: 0)
Press return to continue
```