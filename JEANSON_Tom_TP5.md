# Compte Rendu TP 5 R1.01
**Tom JEANSON** 
**Groupe :** B2
**N° étudiant :** e22601522

## Exercice 1 - Boucles imbriquées
#### Code
```java
/**
* R1.01 - Exercice 1 - Boucles imbriquées
* @author Tom JEANSON
*/
class BoucleImbriquees{
	void principal(){
		testSontTousDiff();
	}
	
	/**
	* vérifie si deux tableaux n’ont aucune valeur commune
	* @param tab1 premier tableau
	* @param tab2 deuxième tableau
	* @return vrai si les tableaux tab1 et tab2 n’ont aucune valeur commune, faux sinon
	*/
	boolean sontTousDiff (int[] tab1, int[] tab2){
		boolean result = true;
		for(int i = 0; i<tab1.length; i++){
			for(int j = 0; j<tab2.length;j++){
				if(tab1[i] == tab2[j]){
					result = false;
				}
			}
		}
		return result;
	}
	
	/**
	* Teste la fonction sontTousDiff()
	*/
	void testSontTousDiff(){
		System.out.println ();
		System.out.println ("*** testSontTousDiff");
		testCasSontTousDiff(new int[]{1,2,3,12},new int[]{5,4,6,13}, true);
		testCasSontTousDiff(new int[]{5}, new int[]{1,2,3,12}, true);
		testCasSontTousDiff(new int[]{5}, new int[]{1,2,3,5}, false);
		testCasSontTousDiff(new int[]{8,45,98,75,4}, new int[]{8,45,98,75,4}, false);
		testCasSontTousDiff(new int[]{8,45,98,75,4}, new int[]{}, true);
		testCasSontTousDiff(new int[]{}, new int[]{8,45,98,75,4}, true);
	}
	
	/**
	* Teste un cas donné de la fonction sontTousDiff()
	* @param tab1 premier tableau
	* @param tab2 deuxième tableau
	* @param result résultat attendu
	*/
	void testCasSontTousDiff(int[] tab1, int[] tab2, boolean result){
		//Affichage
		System.out.print("sontTousDiff(");
		displayTab(tab1);
		System.out.print(") \t= " + result + "\t :");
		
		//Appel
		boolean resExec = sontTousDiff(tab1, tab2);
		
		//Vérification
		if (resExec == result){
		System.out.println ("OK");
		} else {
		System.err.println ("ERREUR");
		}
	}
	
	
	/**
	* Affiche le tableau demandé
	* @param t tableau a afficher
	*/
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
*** testSontTousDiff
sontTousDiff({1,2,3,12}) 	= true	 :OK
sontTousDiff({5}) 	= true	 :OK
sontTousDiff({5}) 	= false	 :OK
sontTousDiff({8,45,98,75,4}) 	= false	 :OK
sontTousDiff({8,45,98,75,4}) 	= true	 :OK
sontTousDiff({}) 	= true	 :OK


------------------
(program exited with code: 0)
Press return to continue
```

## Exercice 2 - Passage par référence - CT 2022
### 1.
#### Code
```java
/**
* R1.01 - Exercice 2 - Passage par référence - CT 2022
* @author Tom JEANSON
*/
class PassageParRef{
	void principal(){
		testDecalerGauche();
	}
	
	/**
	* décale les entiers d’un tableau d’une position vers la gauche
	* L’élément en 0 se retrouve à la fin du tableau
	* @param tab tableau d’entiers
	*/
	void decalerGauche (int[] tab){
		int[] tempoTab = new int [tab.length];
		if(tab.length > 0){
			for(int i = tab.length - 1; i > 0 ; i--){
				tempoTab[i-1] = tab[i];
			}
			tempoTab[tab.length-1] = tab[0];
			for(int i = 0; i < tab.length; i++){
				tab[i] = tempoTab[i];
			}
		}
	}
	
	/**
	* Teste la fonction decalerGauche
	*/
	void testDecalerGauche(){
		int[] test = {1,2,3,4,5,6};
		System.out.println ();
		System.out.println ("*** testDecalerGauche");
		displayTab(test);
		System.out.print("\t => \t");
		decalerGauche(test);
		displayTab(test);
		System.out.println ();
		test = new int[]{4};
		displayTab(test);
		System.out.print("\t => \t");
		decalerGauche(test);
		displayTab(test);
		System.out.println ();
		test = new int[]{};
		displayTab(test);
		System.out.print("\t => \t");
		decalerGauche(test);
		displayTab(test);
		System.out.println ();
		test = new int[]{12,4,5,67,28,54,9};
		displayTab(test);
		System.out.print("\t => \t");
		decalerGauche(test);
		displayTab(test);
		System.out.println ();
		
	}
	
	/**
	* Affiche le tableau demandé
	* @param t tableau a afficher
	*/
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
*** testDecalerGauche
{1,2,3,4,5,6}	 => 	{2,3,4,5,6,1}
{4}	 => 	{4}
{}	 => 	{}
{12,4,5,67,28,54,9}	 => 	{4,5,67,28,54,9,12}


------------------
(program exited with code: 0)
Press return to continue
```
### 2.
#### Code
```java
/**
* R1.01 - Exercice 2 - Passage par référence - CT 2022
* @author Tom JEANSON
*/
class PassageParRef{
	void principal(){
		testDecalerGauche();
	}
	
	/**
	* décale les entiers d’un tableau d’une position vers la gauche
	* L’élément en 0 se retrouve à la fin du tableau
	* @param tab tableau d’entiers
	* @param n entier nombre de cases à décaler
	*/
	void decalerGauche (int[] tab, int n){
		if(tab.length > 0){
			int j = 0;
			while(j < n%tab.length){
				int[] tempoTab = new int [tab.length];
				for(int i = tab.length - 1; i > 0 ; i--){
					tempoTab[i-1] = tab[i];
				}
				tempoTab[tab.length-1] = tab[0];
				for(int i = 0; i < tab.length; i++){
					tab[i] = tempoTab[i];
				}
				j++;
			}
		}
	}
	
	/**
	* Teste la fonction decalerGauche
	*/
	void testDecalerGauche(){
		int[] test = {1,2,3,4,5,6};
		int a = 1;
		System.out.println ();
		System.out.println ("*** testDecalerGauche");
		System.out.print("decalerGauche(");
		displayTab(test);
		System.out.print(", " + a + ")");
		System.out.print("\t => \t");
		decalerGauche(test,a);
		displayTab(test);
		System.out.println ();
		
		a = 0;
		System.out.print("decalerGauche(");
		displayTab(test);
		System.out.print(", " + a + ")");
		System.out.print("\t => \t");
		decalerGauche(test,a);
		displayTab(test);
		System.out.println ();
		
		a = 3;
		System.out.print("decalerGauche(");
		displayTab(test);
		System.out.print(", " + a + ")");
		System.out.print("\t => \t");
		decalerGauche(test,a);
		displayTab(test);
		System.out.println ();
		
		test = new int[]{4};
		a = 1;
		System.out.print("decalerGauche(");
		displayTab(test);
		System.out.print(", " + a + ")");
		System.out.print("\t => \t");
		decalerGauche(test,a);
		displayTab(test);
		System.out.println ();
		
		test = new int[]{};
		a = 5;
		System.out.print("decalerGauche(");
		displayTab(test);
		System.out.print(", " + a + ")");
		System.out.print("\t => \t");
		decalerGauche(test,a);
		displayTab(test);
		System.out.println ();
		
		a = 10;
		test = new int[]{12,4,5,67,28,54,9};
		System.out.print("decalerGauche(");
		displayTab(test);
		System.out.print(", " + a + ")");
		System.out.print("\t => \t");
		decalerGauche(test,a);
		displayTab(test);
		System.out.println ();
		
	}
	
	/**
	* Affiche le tableau demandé
	* @param t tableau a afficher
	*/
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
*** testDecalerGauche
decalerGauche({1,2,3,4,5,6}, 1)	 => 	{2,3,4,5,6,1}
decalerGauche({2,3,4,5,6,1}, 0)	 => 	{2,3,4,5,6,1}
decalerGauche({2,3,4,5,6,1}, 3)	 => 	{5,6,1,2,3,4}
decalerGauche({4}, 1)	 => 	{4}
decalerGauche({}, 5)	 => 	{}
decalerGauche({12,4,5,67,28,54,9}, 10)	 => 	{67,28,54,9,12,4,5}


------------------
(program exited with code: 0)
Press return to continue
```
### 3.
#### Code
```java
/**
* R1.01 - Exercice 2 - Passage par référence - CT 2022
* @author Tom JEANSON
*/
class PassageParRef{
	void principal(){
		testIndiceTab();
	}
	
	/**
	* décale les entiers d’un tableau d’une position vers la gauche
	* L’élément en 0 se retrouve à la fin du tableau
	* @param tab tableau d’entiers
	* @param n entier nombre de cases à décaler
	*/
	void decalerGauche (int[] tab, int n){
		if(tab.length > 0){
			int j = 0;
			while(j < n%tab.length){
				int[] tempoTab = new int [tab.length];
				for(int i = tab.length - 1; i > 0 ; i--){
					tempoTab[i-1] = tab[i];
				}
				tempoTab[tab.length-1] = tab[0];
				for(int i = 0; i < tab.length; i++){
					tab[i] = tempoTab[i];
				}
				j++;
			}
		}
	}
	
	/**
	* Teste la fonction decalerGauche
	*/
	void testDecalerGauche(){
		int[] test = {1,2,3,4,5,6};
		int a = 1;
		System.out.println ();
		System.out.println ("*** testDecalerGauche");
		System.out.print("decalerGauche(");
		displayTab(test);
		System.out.print(", " + a + ")");
		System.out.print("\t => \t");
		decalerGauche(test,a);
		displayTab(test);
		System.out.println ();
		
		a = 0;
		System.out.print("decalerGauche(");
		displayTab(test);
		System.out.print(", " + a + ")");
		System.out.print("\t => \t");
		decalerGauche(test,a);
		displayTab(test);
		System.out.println ();
		
		a = 3;
		System.out.print("decalerGauche(");
		displayTab(test);
		System.out.print(", " + a + ")");
		System.out.print("\t => \t");
		decalerGauche(test,a);
		displayTab(test);
		System.out.println ();
		
		test = new int[]{4};
		a = 1;
		System.out.print("decalerGauche(");
		displayTab(test);
		System.out.print(", " + a + ")");
		System.out.print("\t => \t");
		decalerGauche(test,a);
		displayTab(test);
		System.out.println ();
		
		test = new int[]{};
		a = 5;
		System.out.print("decalerGauche(");
		displayTab(test);
		System.out.print(", " + a + ")");
		System.out.print("\t => \t");
		decalerGauche(test,a);
		displayTab(test);
		System.out.println ();
		
		a = 10;
		test = new int[]{12,4,5,67,28,54,9};
		System.out.print("decalerGauche(");
		displayTab(test);
		System.out.print(", " + a + ")");
		System.out.print("\t => \t");
		decalerGauche(test,a);
		displayTab(test);
		System.out.println ();
		
	}
	
	/**
	* cherche l’indice de la premiere occurrence d’une valeur dans un tableau
	* @param tab tableau d’entiers
	* @param v valeur à chercher
	* @return l’indice de la première valeur v dans tab si v est dans tab, -1 sinon
	*/
	int indiceTab (int[] tab, int v){
		int result = -1;
		int i = 0;
		while(i < tab.length && result == -1){
			if(tab[i] == v){
				result = i;
			}
			i++;
		}
		return result;
	}
	
	/**
	* Teste la fonction indiceTab()
	*/
	void testIndiceTab(){
		System.out.println ();
		System.out.println ("*** testIndiceTab");
		testCasIndiceTab(new int[]{1,2,3,12},1,0);
		testCasIndiceTab(new int[]{1,2,3,12},5,-1);
		testCasIndiceTab(new int[]{},5,-1);
		testCasIndiceTab(new int[]{1,2,3,12,15,16,2},2,1);
	}
	
	/**
	* Teste un cas donné de la fonction indiceTab()
	* @param tab tableau d’entiers
	* @param v valeur à chercher
	* @param result résultat attendu
	*/
	void testCasIndiceTab(int[] tab, int v, int result){
		//Affichage
		System.out.print("indiceTab(");
		displayTab(tab);
		System.out.print(", " + v + ") \t= " + result + "\t :");
		
		//Appel
		int resExec = indiceTab(tab,v);
		
		//Vérification
		if (resExec == result){
		System.out.println ("OK");
		} else {
		System.err.println ("ERREUR");
		}
	}
	
	
	
	
	/**
	* Affiche le tableau demandé
	* @param t tableau a afficher
	*/
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
*** testIndiceTab
indiceTab({1,2,3,12}, 1) 	= 0	 :OK
indiceTab({1,2,3,12}, 5) 	= -1	 :OK
indiceTab({}, 5) 	= -1	 :OK
indiceTab({1,2,3,12,15,16,2}, 2) 	= 1	 :OK


------------------
(program exited with code: 0)
Press return to continue
```
### 4.
#### Code
```java
/**
* R1.01 - Exercice 2 - Passage par référence - CT 2022
* @author Tom JEANSON
*/
class PassageParRef{
	void principal(){
		testDecaleValeur();
	}
	
	/**
	* décale les entiers d’un tableau d’une position vers la gauche
	* L’élément en 0 se retrouve à la fin du tableau
	* @param tab tableau d’entiers
	* @param n entier nombre de cases à décaler
	*/
	void decalerGauche (int[] tab, int n){
		if(tab.length > 0){
			int j = 0;
			while(j < n%tab.length){
				int[] tempoTab = new int [tab.length];
				for(int i = tab.length - 1; i > 0 ; i--){
					tempoTab[i-1] = tab[i];
				}
				tempoTab[tab.length-1] = tab[0];
				for(int i = 0; i < tab.length; i++){
					tab[i] = tempoTab[i];
				}
				j++;
			}
		}
	}
	
	/**
	* Teste la fonction decalerGauche
	*/
	void testDecalerGauche(){
		int[] test = {1,2,3,4,5,6};
		int a = 1;
		System.out.println ();
		System.out.println ("*** testDecalerGauche");
		System.out.print("decalerGauche(");
		displayTab(test);
		System.out.print(", " + a + ")");
		System.out.print("\t => \t");
		decalerGauche(test,a);
		displayTab(test);
		System.out.println ();
		
		a = 0;
		System.out.print("decalerGauche(");
		displayTab(test);
		System.out.print(", " + a + ")");
		System.out.print("\t => \t");
		decalerGauche(test,a);
		displayTab(test);
		System.out.println ();
		
		a = 3;
		System.out.print("decalerGauche(");
		displayTab(test);
		System.out.print(", " + a + ")");
		System.out.print("\t => \t");
		decalerGauche(test,a);
		displayTab(test);
		System.out.println ();
		
		test = new int[]{4};
		a = 1;
		System.out.print("decalerGauche(");
		displayTab(test);
		System.out.print(", " + a + ")");
		System.out.print("\t => \t");
		decalerGauche(test,a);
		displayTab(test);
		System.out.println ();
		
		test = new int[]{};
		a = 5;
		System.out.print("decalerGauche(");
		displayTab(test);
		System.out.print(", " + a + ")");
		System.out.print("\t => \t");
		decalerGauche(test,a);
		displayTab(test);
		System.out.println ();
		
		a = 10;
		test = new int[]{12,4,5,67,28,54,9};
		System.out.print("decalerGauche(");
		displayTab(test);
		System.out.print(", " + a + ")");
		System.out.print("\t => \t");
		decalerGauche(test,a);
		displayTab(test);
		System.out.println ();
		
	}
	
	/**
	* cherche l’indice de la premiere occurrence d’une valeur dans un tableau
	* @param tab tableau d’entiers
	* @param v valeur à chercher
	* @return l’indice de la première valeur v dans tab si v est dans tab, -1 sinon
	*/
	int indiceTab (int[] tab, int v){
		int result = -1;
		int i = 0;
		while(i < tab.length && result == -1){
			if(tab[i] == v){
				result = i;
			}
			i++;
		}
		return result;
	}
	
	/**
	* Teste la fonction indiceTab()
	*/
	void testIndiceTab(){
		System.out.println ();
		System.out.println ("*** testIndiceTab");
		testCasIndiceTab(new int[]{1,2,3,12},1,0);
		testCasIndiceTab(new int[]{1,2,3,12},5,-1);
		testCasIndiceTab(new int[]{},5,-1);
		testCasIndiceTab(new int[]{1,2,3,12,15,16,2},2,1);
	}
	
	/**
	* Teste un cas donné de la fonction indiceTab()
	* @param tab tableau d’entiers
	* @param v valeur à chercher
	* @param result résultat attendu
	*/
	void testCasIndiceTab(int[] tab, int v, int result){
		//Affichage
		System.out.print("indiceTab(");
		displayTab(tab);
		System.out.print(", " + v + ") \t= " + result + "\t :");
		
		//Appel
		int resExec = indiceTab(tab,v);
		
		//Vérification
		if (resExec == result){
		System.out.println ("OK");
		} else {
		System.err.println ("ERREUR");
		}
	}
	
	/**
	* décale les valeurs d’un tableau de manière à ramener la valeur cherchée
	* à l’indice 0
	* Si la valeur n’est pas présente, le tableau n’est pas modifié
	* @param tab tableau d’entiers
	* @param v valeur à chercher
	*/
	void decaleValeur (int[] tab, int v){
		int decalage = indiceTab(tab, v);
		decalerGauche(tab,decalage);
	}
	
	/**
	* Teste la fonction decalerGauche
	*/
	void testDecaleValeur(){
		int[] test = {1,2,3,4,5,6};
		int a = 1;
		System.out.println ();
		System.out.println ("*** testDecaleValeur");
		System.out.print("decaleValeur(");
		displayTab(test);
		System.out.print(", " + a + ")");
		System.out.print("\t => \t");
		decaleValeur(test,a);
		displayTab(test);
		System.out.println ();
		
		test = new int[]{4};
		a = 1;
		System.out.print("decalerGauche(");
		displayTab(test);
		System.out.print(", " + a + ")");
		System.out.print("\t => \t");
		decaleValeur(test,a);
		displayTab(test);
		System.out.println ();
		
		test = new int[]{};
		a = 5;
		System.out.print("decalerGauche(");
		displayTab(test);
		System.out.print(", " + a + ")");
		System.out.print("\t => \t");
		decaleValeur(test,a);
		displayTab(test);
		System.out.println ();
		
		test = new int[]{1,2,3,4,5,6,7,1,4,5,8,7,4,9};
		a = 4;
		System.out.print("decalerGauche(");
		displayTab(test);
		System.out.print(", " + a + ")");
		System.out.print("\t => \t");
		decaleValeur(test,a);
		displayTab(test);
		System.out.println ();
		
		a = 47;
		System.out.print("decalerGauche(");
		displayTab(test);
		System.out.print(", " + a + ")");
		System.out.print("\t => \t");
		decaleValeur(test,a);
		displayTab(test);
		System.out.println ();
	}
	
	/**
	* Affiche le tableau demandé
	* @param t tableau a afficher
	*/
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
*** testDecaleValeur
decaleValeur({1,2,3,4,5,6}, 1)	 => 	{1,2,3,4,5,6}
decalerGauche({4}, 1)	 => 	{4}
decalerGauche({}, 5)	 => 	{}
decalerGauche({1,2,3,4,5,6,7,1,4,5,8,7,4,9}, 4)	 => 	{4,5,6,7,1,4,5,8,7,4,9,1,2,3}
decalerGauche({4,5,6,7,1,4,5,8,7,4,9,1,2,3}, 47)	 => 	{4,5,6,7,1,4,5,8,7,4,9,1,2,3}


------------------
(program exited with code: 0)
Press return to continue
```

## Exercice 3 - Valeurs différentes
### Code
```java
/**
* R1.01 - Exercice 3 - Valeurs différentes
* @author Tom JEANSON
*/
class ValDiff{
	void principal(){
		testCompteDiffVal();
	}
	
	/**
	* compte le nombre de valeurs différentes dans un tableau
	* @param tab tableau d’entiers
	* @return le nombre de valeurs différentes du tableau
	*/
	int compteDiffVal(int[] tab){
		int nbrValDiff = 0;
		int [] valConnu = new int [tab.length];
		for(int i = 0; i < tab.length; i++){
			boolean different = true;
			int j = 0;
			while(j < nbrValDiff && different){
				if(tab[i] == valConnu[j]){
					different = false;
				}
				j++;
			}
			if(different){
				valConnu[j] = tab[i];
				nbrValDiff ++;
			}
		}
		return nbrValDiff;
	}
	
	/**
	* Teste la fonction compteDiffVal()
	*/
	void testCompteDiffVal(){
		System.out.println ();
		System.out.println ("*** testCompteDiffVal");
		testCasCompteDiffVal(new int[]{1,1,1,1},1);
		testCasCompteDiffVal(new int[]{1,2,3,4},4);
		testCasCompteDiffVal(new int[]{},0);
		testCasCompteDiffVal(new int[]{1,2,3,1,2,3},3);
	}
	
	/**
	* Teste un cas donné de la fonction compteDiffVal()
	* @param tab tableau d’entiers
	* @param result résultat attendu
	*/
	void testCasCompteDiffVal(int[] tab, int result){
		//Affichage
		System.out.print("compteDiffVal(");
		displayTab(tab);
		System.out.print(") \t= " + result + "\t :");
		
		//Appel
		int resExec = compteDiffVal(tab);
		
		//Vérification
		if (resExec == result){
		System.out.println ("OK");
		} else {
		System.err.println ("ERREUR");
		}
	}
	
	/**
	* Affiche le tableau demandé
	* @param t tableau a afficher
	*/
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
### Sortie
```java
*** testCompteDiffVal
compteDiffVal({1,1,1,1}) 	= 1	 :OK
compteDiffVal({1,2,3,4}) 	= 4	 :OK
compteDiffVal({}) 	= 0	 :OK
compteDiffVal({1,2,3,1,2,3}) 	= 3	 :OK


------------------
(program exited with code: 0)
Press return to continue
```
## Exercice 4
#### Code
```java
/**
 * R1.01 - Exercice 4 - Sous-chaînes
 * @author Tom JEANSON
 */
class SousChaines{
	void principal(){
		testEstSousChaine();
	}
	/**
	* teste si une chaîne est une sous-chaîne d’une autre
	* @param mot chaîne de caractères
	* @param phrase chaîne de carectères
	* @return vrai ssi mot est présent dans phrase
	*/
	boolean estSousChaine (String mot, String phrase){
		boolean res = false;
		int i = 0;
		int j = 0;
		while(i < phrase.length() - 1 && !res){
			if(phrase.charAt(i) == mot.charAt(j)){
				j++;
				if(j == mot.length() - 1){
					res = true;
				}
			}
			else {
				j = 0;
			}
			i++;
		}
		return res;
	}
	
	/**
	* Teste la fonction estSousChaine()
	*/
	void testEstSousChaine(){
		System.out.println ();
		System.out.println ("*** testEstSousChaine");
		testCasEstSousChaine("ses","ses",true);
		testCasEstSousChaine("ses","abcdsesdef",true);
		testCasEstSousChaine("ses","abcdef",false);
		testCasEstSousChaine("ses","abscdefse",false);
		testCasEstSousChaine("ses","abkzeodlmzpses",true);
	}
	
	/**
	* Teste un cas donné de la fonction estSousChaine()
	* @param mot chaîne de caractères
	* @param phrase chaîne de carectères
	* @param result résultat attendu
	*/
	void testCasEstSousChaine(String mot, String phrase, boolean result){
		//Affichage
		System.out.print("estSousChaine(" + mot + ", " + phrase + ") \t= " + result + "\t :");
		
		//Appel
		boolean resExec = estSousChaine(mot,phrase);
		
		//Vérification
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
*** testEstSousChaine
estSousChaine(ses, ses) 	= true	 :OK
estSousChaine(ses, abcdsesdef) 	= true	 :OK
estSousChaine(ses, abcdef) 	= false	 :OK
estSousChaine(ses, abscdefse) 	= false	 :OK
estSousChaine(ses, abkzeodlmzpses) 	= true	 :OK


------------------
(program exited with code: 0)
Press return to continue
```
## Exercice 5 - Tri
#### Code
```java
/**
 * R1.01 - Exercice 5 - Tri
 * @author Tom JEANSON
 */
class Tri{
	final int LG_TAB = 10;
	void principal(){
		displayTab(saisirEtTrier());
	}
	
	/**
	* Crée et saisit un tableau trié de LG_TAB entiers
	* @return tableau trié de LG-TAB entiers
	*/
	int[] saisirEtTrier () {
		int[] t = new int[LG_TAB];
		int i = 0;
		
		while (i < t.length) {
			t[i] = SimpleInput.getInt ("Entrer un entier : ");
			
			// insertion de la valeur en ordre croissant dans t
			int j = i;
			int a = t[i];
			while(j > 0 && a < t[j-1] ){
				t[j] = t[j-1];
				j--;
			}
			t[j] = a;
			i = i + 1;
		}
		return t;
	}
	
	/**
	* Affiche le tableau demandé
	* @param t tableau a afficher
	*/
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
Entrer un entier : 10
Entrer un entier : 9
Entrer un entier : 8
Entrer un entier : 7
Entrer un entier : 6
Entrer un entier : 5
Entrer un entier : 4
Entrer un entier : 3 
Entrer un entier : 2
Entrer un entier : 1
{1,2,3,4,5,6,7,8,9,10}

------------------
(program exited with code: 0)
Press return to continue
```
```java
Entrer un entier : 5
Entrer un entier : 10
Entrer un entier : 15
Entrer un entier : 25
Entrer un entier : 30
Entrer un entier : 1
Entrer un entier : 7
Entrer un entier : 12
Entrer un entier : 22
Entrer un entier : 27
{1,5,7,10,12,15,22,25,27,30}

------------------
(program exited with code: 0)
Press return to continue
```
```java
Entrer un entier : 1
Entrer un entier : 1
Entrer un entier : 1
Entrer un entier : 1
Entrer un entier : 1
Entrer un entier : 0
Entrer un entier : 5
Entrer un entier : 5
Entrer un entier : 5
Entrer un entier : 4
{0,1,1,1,1,1,4,5,5,5}

------------------
(program exited with code: 0)
Press return to continue
```
```java
Entrer un entier : 1
Entrer un entier : 2
Entrer un entier : 3
Entrer un entier : 4
Entrer un entier : 5
Entrer un entier : 6
Entrer un entier : 7
Entrer un entier : 8
Entrer un entier : 9
Entrer un entier : 10
{1,2,3,4,5,6,7,8,9,10}

------------------
(program exited with code: 0)
Press return to continue
```