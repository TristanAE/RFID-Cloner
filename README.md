# RFID-Copier
Elaboration d'un boitier dans lequel est caché un lecteur RFID pour enregistrer automatiquement des cartes.


# I-	Conception électronique 


Pour concevoir le projet, j’ai opté pour l’utilisation d’une carte Nodemcu car je disposais d’un câble micro USB C plus petit et plus souple que celui d’une carte Arduino Nano.


a)	Alimentation de la carte


Pour pouvoir alimenter la carte via le port micro USB C de la Nodemcu j’utiliserai un support de pile 6V dont les fils électriques sont déjà soudés, ainsi qu’un mini module PCB USB femelle afin de pouvoir envoyer le courant des piles vers le câble USB de la Nodemcu.

  ![femelle](https://user-images.githubusercontent.com/92324336/146688033-2be75e49-b003-46c4-baf3-f88e375bb0e5.jpg)   ![support](https://user-images.githubusercontent.com/92324336/146688065-9ee2e1ac-fd64-4ab7-bf0a-6f4c64606a59.jpg)  



 


Il faut ensuite pouvoir contrôler lorsqu'on le souhaite l'allumage de la carte grâce à un bouton levier. 
                             
![bouton](https://user-images.githubusercontent.com/92324336/146691155-1fd6810b-bc60-4d89-8d2e-17d0e8796d46.png)



•	On soude le pôle positif des piles au bouton

•	On soude l’autre broche du bouton vers le Vbus du module femelle USB. Le courant ne passe que si le levier est actionné.

•	On soude le pôle négatif des piles vers le GND du module USB femelle


b)	Module RFID et led indicatrice


Pour brancher le module RFID à la carte :

 ![Node](https://user-images.githubusercontent.com/92324336/146691266-ae3609b8-8e0a-4d49-b65d-4e3708bf275e.png)

https://github.com/bernardo-amaral/nodemcu-rfid

On branche également une led RGB sur 3 différents pins pour obtenir trois couleurs indiquant l’avancée de la copie depuis l’extérieur.
 
![RGB](https://user-images.githubusercontent.com/92324336/146691283-8b3b05c3-f295-477b-adbe-c1c8952166c2.jpg)

# II-	Conception informatique


Pour mettre au point un copieur de carte RFID automatique, nous utilisons le code d’exemple fourni avec la bibliothèque RFID.
Après modification de ce code pour nos besoins, le programme enchaine infiniment et successivement ces évènements :

•	Allumage de la led en rouge et attente d’une carte à copier sur le lecteur

•	Détection d’une carte puis copie de celle-ci.

•	Allumage de la led en bleu et attente d’une carte programmable

•	Détection de la 2nd carte puis copie des éléments dans celle-ci

•	Allumage de la led en vert 3 secondes puis en rouge 

Si un traitement n’est pas correctement réalisé, l’étape en cours recommence.



# III-	Conception 3D


La boite dans laquelle se trouvera notre copieur de badge est séparée en deux parties :
-	Une zone de rangement de tous les modules avec les trous pour la led et le bouton
-	Une zone sans composant qui permettra de tromper la cible
-	Chaque bloc est séparé par une cloison et fermable avec un couvercle

![IMRPIMANTE](https://user-images.githubusercontent.com/92324336/146691290-49cc0106-2397-4397-b905-647404c3f901.png)

 

# Rendu final!

![20211211_183354](https://user-images.githubusercontent.com/92324336/146691714-1b6b41a2-49d6-4e5d-b70b-2685f8200160.jpg)


![ezgif com-gif-maker (1)](https://user-images.githubusercontent.com/92324336/146691466-67b8a1af-acb9-4eb3-a965-051acef23675.gif)






