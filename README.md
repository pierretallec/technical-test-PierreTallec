# Technical test

## Bug fixés

### Premier bug

Dans l'onglet "people" du site, lorsque au'on cliquait sur un utilisateur pour modifier ses données, le bouton "update" ne fonctionnait pas.
Pour régler ce problème, j'ai ajouté une balise Button et j'ai changer l'événement onChange en onClick

##### app/src/scenes/user/view.js line 136

### Deuxième bug

Toujours dans l'onglet "people", lorsqu'on créait un nouvel utilisateur, le nom n'était pas envoyé à la base de donnée. Ainsi, il n'apparaissait nul part sur l'interface après la création.
Pour régler ce problème, j'ai modifier la valeur de name 'username' par 'name' dans la balise input pour correspondre aux champs dans la base de donnée.

##### app/src/scenes/user/list.js line 131

### Troisième bug

Lorsqu'on cliquait sur l'onglet projet, une erreure apparaissait.
J'ai compris que c'était parce qu'on essayait d'accéder au champ \_id de l'objet "projet" obtenu depuis la base de donnée alors que projet était une liste de un seul item.
J'ai d'abord essayé de restructurer projet dans le front de l'application, puis j'ai réaliser qu'il y avait une solution plus simple.
J'ai fixé ce bug en changeant la fonction "find" par "findOne" dans le controller project.js. Ainsi, j'obtenait les résultat au format voulu dans le front.

##### api/src/controllers/project ligne 22

## Quick Win Feature

### Première feature

J'ai d'abord implémenté un système de bloquage d'accès au site après trop de tentatives d'identifications ratées. Je pense que cette feature est importante pour toutes les plateformes. C'est un moyen simple de sécuriser les données des utilisateurs contre les attaques par brute force

Cependant, bien que cette feature soit importante, elle ne me semblait pas assez créative, ce pourquoi j'ai implementé la deuxième feature.

### Deuxième feature

J'ai implémenter un système d'envoie de mail lorsque une adresse mail est préciser dans les données d'un utilisateur. Cette fonctionnalité pourrait être utilisée pour signaler à une personne qu'il a été ajouté à un projet par exemple.
