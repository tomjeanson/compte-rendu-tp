# Aide-mémoire Markdown (Pense-bête complet)

Ce document récapitule toutes les synthèses et fonctionnalités Markdown (standard, avancées et HTML) pour vous servir de guide pratique au quotidien.

---

## 1. Titres (Headings)

```markdown
# Titre de niveau 1 (H1)
## Titre de niveau 2 (H2)
### Titre de niveau 3 (H3)
#### Titre de niveau 4 (H4)
##### Titre de niveau 5 (H5)
###### Titre de niveau 6 (H6)
```

---

## 2. Formatage du texte

```markdown
**Texte en gras** ou __Texte en gras__
*Texte en italique* ou _Texte en italique_
***Texte en gras et italique***
~~Texte barré~~
<font color='red'>Texte en rouge</font>
<font color='blue'>Texte en bleu</font>
<font color='green'>Texte en vert</font>
```

---

## 3. Listes

### Liste non ordonnée (à puces)
```markdown
* Élément 1
* Élément 2
  * Sous-élément 2.1
  * Sous-élément 2.2
* Élément 3
```
*(Vous pouvez aussi utiliser `-` ou `+` à la place de `*`)*

### Liste ordonnée (numérotée)
```markdown
1. Élément 1
2. Élément 2
3. Élément 3
```

### Liste de tâches (Checklist)
```markdown
- [x] Tâche terminée
- [ ] Tâche à faire
```

---

## 4. Liens et Images

### Liens hypertextes
```markdown
[Texte du lien](https://www.example.com)
[Lien avec titre](https://www.example.com "Titre au survol")
```

### Images
```markdown
![Texte alternatif](lien_ou_id_de_image)
```

### Image cliquable (Lien derrière une image)
```markdown
[![Texte alternatif](lien_de_l_image)](lien_de_redirection)
```

---

## 5. Citations

```markdown
> Ceci est une citation.
> 
> Elle peut comporter plusieurs paragraphes.
>> Et des citations imbriquées.
```

---

## 6. Ligne horizontale (Séparateur)

```markdown
---
```
*(Ou `***` ou `___`)*

---

## 7. Code et Blocs de Code

### Code en ligne
```markdown
Utiliser la commande `git status` pour voir l'état.
```

### Bloc de code avec coloration syntaxique
````markdown
```python
def saluer(nom):
    print(f"Bonjour, {nom} !")
```
````

````markdown
```html
<div class="conteneur">
    <p>Bonjour le monde</p>
</div>
```
````

---

## 8. Tableaux

```markdown
| En-tête 1 | En-tête 2 | En-tête 3 |
| :--- | :---: | ---: |
| Aligné à gauche | Centré | Aligné à droite |
| Texte | Texte | Texte |
```

---

## 9. Notes de bas de page & Échappement

### Échapper des caractères spéciaux
Pour afficher un caractère réservé sans qu'il soit interprété par Markdown, utilisez un anti-slash `\`.
```markdown
\* Pas une puce \*
\# Pas un titre
```

### Subscript (Indice) et Superscript (Exposant) *(selon éditeur/HTML)*
```markdown
H<sub>2</sub>O (Eau)
E = mc<sup>2</sup>
```
