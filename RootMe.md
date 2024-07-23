# Root Me Challenge
https://www.root-me.org/fr/Challenges/Web-Serveur/HTTP-POST

<hr>

## Objectif  : **Trouver une façon de battre le meilleur score**
  
### Synopsys :  

> Ici pour lancer le jeu on clique sur le bouton **`Give a try !`**.
Si l'on fait moins que le meilleur score **`999999`** on perd. Le but étant de battre ce score...

**Que se passe t'il en cliquant sur le bouton ?** 
... That is a question.

> En cliquant sur le bouton cela va envoyer une requête (demande) d'un certain type au serveur web via le protocol **HTTP** (_hyperText Transfert Protocol_) qui traitera la demande et renverra le résulat dans un navigateur. C'est un protocole dit : client / serveur.  <br>

> Le type ou la méthode ici est **POST**. La méthode POST écrit les paramètres URL dans la requête HTTP pour le serveur. Les paramètres ne sont donc pas visibles pour les utilisateurs contrairement à la méthode GET qui envoie en clair les données dans l'URL (_Uniform Ressource Locator_).

- https://www.ionos.fr/digitalguide/sites-internet/developpement-web/get-vs-post/#c251633
 

> L'URL est du mécanisme utilisé par les navigateurs pour accéder à toute ressource publiée sur le net. l’URL équivaut à l'adresse postale du facteur. Cette adresse est ainsi utilisée pour pouvoir accéder à une page d'un site internet telle que la page d'accueil, la page de contacts... 

    Elle peut-être composée :
    - Du protocol
    - D'un nom de domaine et sous-domaine
    - D'un chemin
    - et de paramètre ou requête (après le ?)  

- https://www.numacom.fr/blog/qu-est-ce-qu-une-url-definition-et-fonctionnement


**HTTP est avec HTML et les URL une des trois inventions fondamentales de Tim Berners-Lee pour créer le World Wide Web.**

<br>

## Une fois la page du jeu affichée :

Ici le but est d'afficher le code pour le hacker, de façon à gagner en faisant plus que 999999.

### Méthodologie: 

- Ouvrir l'inspecteur (F12).
  
    - Trouver la ligne de code qui permet l'envoie de la requête. 
    - 
        Indice ...
        - _Celle-ci est envoyée avec la méthode POST via un formulaire._
  
        ### Explication :

        ```html
        <form action="" method="post" onsubmit="document.getElementsByName('score')[0].value = Math.floor(Math.random() * 1000001)">
            <input type="hidden" name="score" value="-1" />
            <input type="submit" name="generate" value="Give a try!">
        </form>
        ```        

       **↑** Ce morceau de code HTML avec du Javascript ci-dessus, comprend un formulaire contenant un champ caché et un bouton de soumission. 
       <br>

       ### De façon plus précise ...

        ```html
        <form action="" method="post" onsubmit="document.getElementsByName('score')[0].value = Math.floor(Math.random() * 1000001)">
        <form>
        ```  
      
       └> Définit un formulaire HTML.

        - **action=""** : Spécifie l'URL vers laquelle les données du formulaire doivent être envoyées. Une valeur vide signifie que le formulaire sera soumis à la même URL que la page actuelle.
  
        - **method="post"** : Indique que les données du formulaire seront envoyées via une requête HTTP en POST.
  
        - **onsubmit="..."** : Attribut JavaScript, qui spécifie une fonction ou un script à exécuter lorsque le formulaire est soumis. Ici, le script JavaScript change la valeur du champ caché `score` avant la soumission du formulaire.
  
        Fonction JS :
        - **Math. floor(x)** renvoie le plus grand entier qui est inférieur ou égal à un nombre x.
  
        - **Math.random()** renvoie un nombre flottant pseudo-aléatoire, généré entre 0 (inclus) et 1 (exclu)”.








TchatGPT : https://chatgpt.com/c/bc5bb0de-f2fa-4a38-b38f-4a1efa52bc86