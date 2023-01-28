

<!-- Preview = Ctrl + Maj + V -->


# Utilisation du DOM grâce à JavaScript.
#### Les différentes méthodes.

**Sélection en fonction du document.**
```bash

document.getElementById("main") # récupère l'élément ayant l'ID "main"

document.getElementsByClassName("modal") # récupère les éléments ayant la classe "modal".

document.getElementsByTagName() # récupère les éléments ayant le même nom de balise correspondant. 
# Exemple : document.getElementsByTagName(a) -> récupère tous les boutons "a"

document.querySelector("div") # récupère le premier élément correspondant à une div.
document.querySelector(".modal") # récupère le premier élément correspondant à une classe "modal". 

const nav = document.querySelectorAll('li') # récupère l'ensemble des élément correspondants à la balise li. -> Tableau d'éléments.
```

*********
**Il est possible de sélectionner un élément indirectement:**

```bash
element.children # retourne la liste enfant.
element.parentElement # retourne l'élément parent.
element.nextElementSibling # naviguer avec les éléments suivants.
element.previousElementSibling # naviguer avec les éléments précédents.
```


*********


**Agir sur un attribut d'un élément:**
```bash
element.classList.add("maclasse") # ajoute la classe à mon élément
element.classList.remove("maclasse") # supprime la classe à mon élément
element.classList.contains("maclasse") # return true or false si mon élément correspond à cette classe
element.classList.replace("firstclass", "secondclass") # remplace firstclass par secondclass.

element.style.backgroundColor = '#000' # change la couleur de l'élément en blanc.

element.setAttribute(name, valeur)
	#Ex: (Notre element correspond à un input)
	element.setAttribute('type', 'password') # change le type de l'input en type password.
	element.setAttribute('class', 'myClass') # ajoute la classe "myClass" à mon élément.
```
****
#### Créer un élément via la DOM et l'insérer dans l'HTML.
##### Étape 1: Créer l'élément
```bash
const newElement = document.createElement("div") # Création d'une div.
#  Notre élément ne fait pas encore partie du document.
```
##### Étape 2: Ajouter notre élément créé à un parent existant.
```bash
# Déclaration de notre div qui sera le parent de notre élément.
let mainDiv = document.getElementById('main'); # Ici, notre div "main" existe déjà en HTML.
#Application de la méthode appenChild(enfant). 
#Elle permet de désigner en paramètre l'élément à intégrer en tant qu'enfant.
mainDiv.appendChild(newElement);
```

##### Code final:
```bash
const newElement = document.createElement("div");
let mainDiv = document.getElementById('main');  

mainDiv.appendChild(newElement);

console.log(mainDiv) 	# <div id="main">
console.log(newElement) # <div>

# structure html obtenue: 
<div id="main">
  <div></div>
</div>
```

