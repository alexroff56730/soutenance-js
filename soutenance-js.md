                KATA JS 1 :

Dans cette exercice on nous demande de faire un "switch case",
qui retourne pour chaque case la valeur de la variable "name", ici "name" est retourné par les différents "switch case", à "switch(id){}".

```js
function getPlanetName(id){
  var name;
  //création du switch
  switch(id){
  //creation du conteneur case
    case 1:
    //on initialise name en lui donnant une valeur au choix
      name = 'Mercury'
      //on le retourne au switch(id) et id contient maintenant name
      return name
    case 2:
      name = 'Venus'
      return name
  }
}
```

Mais ici nous voulons que ce soit la fonction "getPlanetName(id)" qui retourne id, donc une fois tous les "switch case" réalisé,
on indique dans le programme qu'il faut lui retourner id :

```js
//création de la fonction qui à qui on retourne l'élément id
function getPlanetName(id){
//variable name qui sera retournée à id
  var name;
  switch(id){
    //code précédent ci-dessus
  }
  /*on retourne id qui contient name via les switch case à la fonction*/
  return id;
}
```

Une fois id retourner la fonction vaudra "id" qui lui vaux "name" donc la fonction vaudra aussi "name" qui donc pourra nous donner les différente valeur attendu dans le "switch case".

              KATA JS 2 :

Ici nous devons inverser les nombres positif en nombre négatif, les nombre sont donner dans un tableau :

```js
//on créer la fonction
function invert(array) {
    //on crée un tableau
    let tab = [];
      /*on créer une boucle avec comme condition :
            * la création de la variable i (qui sera égale à l'index de notre tableau)
            
            * si i est inférieure à array.length
            
            * rajoute 1 à i (i++)*/
      for (let i = 0; i < array.length; i++) {
      //instruction de la boucle :
         tab.push(-array[i]);
    }
  }
```
push nous permet d'ajouter une valeur dans le tableaux qui n'est pas définit dans celui-ci, donc ici on lui ajoute dans tab la valeur du tableau array avec l'index [i] et la valeur sera inverser avec le symbole "-" donc

```js
tab.push(-array[i]);
```

Pour le moment oui le programme change bien les nombres positif en nombre négatif, mais la fonction ne renvoie rien car nous ne lui retournons aucune valeur !

```js
function invert(array) {
    let tab = [];

      for (let i = 0; i < array.length; i++) {
         tab.push(-array[i]);
    }
    //on retourne le tableau à la fonction
    return tab;
  }
```

Et donc si l'on donne à la fonction la valeur tab aprés la boucle "for" grace à :

```js
return tab;
```

Puis que l'on donne l'instruction aprés la fonction :

```js
invert([1,2,3,4,5]);
```

La fonction dans la console nous retournera :

```
[-1, -2, -3, -4, -5];
```
Pour ce KATA j'ai eu plus de dificulté car dans l'instruction de la boucle j'ai donner :

```js
for (let i = 0; i < array.length; i++;) {
  tab.push(-i);
}
```

Mon erreur est que c'est l'index qui étais inversé, et pas les valeur du tableau array.

        KATA js 3

Dans ce KATA il faut vérifier si le nombre number est divisible par a et par b si une des deux conditions est fausse, toute la fonction retourne false :

```js
function isDivideBy(number, a, b) {
//si number%a == 0 et number%b == 0 sont vrais
  if (number%a == 0 && number%b == 0) {
    return true;//retourne vrais
  } else { //sinon
    return false;//retourne faux
  }
}
```

Pour vérifiez cela, il nous faut dans notre code une condition si number et divisible par a et b :

```js
if (number%a == 0 && number%b == 0){
  return true;
  }
```

La condition n'est pas totalement gérer car si la condition retourne false rien ne ce passera, donc on utilise else pour lui dire sinon :

```js
if (number%a == 0 && number%b == 0) {
    return true;
  } else /*sinon : */ {
    return false;//retourne faux
  }
```

Et le programme retournera false si number n'est pas divisible par a et b

        KATA JS 4 :
        
Je n'est pas vraiment réussi ce KATA, car ce qui été demandé été de faire un correcteur automatique et dans ce programme on ne peux corriger seulement les mots qu'il "connait" :

```js
function correct(string) {
//tableau des erreur dans les différent mots
  let stringError = [/0/gi, /5/gi, /1/gi, /51/gi, /15/gi];
  
  
//tableau correction
  let stringCorrect = ["O", "S", "I", "SI", "IS"];
  
  
//variable que l'on retourne pour changer les nombres par des lettres
  let stringChange = "";
  
  
  //condition
  if (string == "L0ND0N") {
    stringChange = string.replace(stringError[0], stringCorrect[0]);
  } else if (string == "DUBL1N"){
    stringChange = string.replace(stringError[2], stringCorrect[2]);
  } else if (string == "51GAP0RE") {
    stringChange = string.replace(stringError[3], stringCorrect[3]);
      if(stringChange == "SINGAP0RE") {
      stringChange = stringChange.replace(stringError[0], stringCorrect[0]);
      } else {
      console.log("ERROR");
     }
  } else if (string == "BUDAPE5T") {
    stringChange = string.replace(stringError[1], stringCorrect[1]);
  } else if (string == PAR15) {
    stringChange = string.replace(strinError[4], stringCorrect[4]);
  } else {
    console.log("je ne connais pas ce mot !!!");
  }
}
```

