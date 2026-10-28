## TP4 — Model Registry et API FastAPI

### 1. Comment désigner officiellement le modèle à utiliser ?

Le Model Registry de MLflow permet d'enregistrer les modèles et de leur attribuer des versions. L'alias `champion` désigne la version sélectionnée comme modèle de référence. Il peut être déplacé vers une autre version sans modifier le nom du modèle utilisé dans le code.

### 2. Comment une application peut-elle utiliser le modèle ?

Une application peut envoyer les données d'un client à l'API FastAPI avec une requête HTTP `POST` vers `/predict`. Les données sont transmises au format JSON et l'API renvoie la prédiction du modèle, indiquant si le client risque de partir ou de rester.

### 3. Que se passe-t-il quand on change de champion ?

Il suffit de déplacer l'alias `champion` vers la nouvelle version du modèle dans le Registry. L'API doit ensuite être redémarrée pour charger cette nouvelle version. Le code de l'API et celui des applications clientes restent inchangés.