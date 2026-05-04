#LabThreadsAsyncTask

Application Android en Java illustrant l’exécution de traitements longs sans bloquer l’interface utilisateur grâce aux **Threads** et à **AsyncTask**.


##Objectif

Comprendre comment garder une interface fluide en Android en séparant :
- le **UI Thread** (affichage et interactions)
- le **Worker Thread** (tâches longues)



##Fonctionnalités

- Charger une image avec un Thread (background)
- Effectuer un calcul lourd avec AsyncTask
- Afficher un Toast instantanément (UI non bloquée)
- Afficher une ProgressBar avec progression


##Concepts utilisés

###UI Thread
- Gère l’affichage (TextView, ImageView, boutons)
- Ne doit jamais être bloqué

###Worker Thread
- Exécute les tâches longues (calcul, chargement)
- Ne peut pas modifier directement l’UI

###Mise à jour de l’UI
Méthodes utilisées :
- Handler (Looper.getMainLooper())
- view.post(...)
- runOnUiThread(...)

###AsyncTask (pédagogique)
- onPreExecute() → préparation UI
- doInBackground() → traitement en fond
- onProgressUpdate() → mise à jour progression
- onPostExecute() → affichage du résultat



##Interface

L’application contient :
- TextView (statut)
- ProgressBar (progression)
- ImageView (image)
- 3 boutons :
  - Charger image (Thread)
  - Calcul lourd (AsyncTask)
  - Afficher Toast



##Structure

com.example.labthreadsasynctask  
└── MainActivity.java  



##Installation

1. Cloner le projet   

2. Ouvrir avec Android Studio  

3. Lancer sur un émulateur ou appareil réel  



##Test

- Cliquer sur "Charger image (Thread)"
- Cliquer sur "Afficher Toast" pendant le chargement  
  Le Toast doit s’afficher immédiatement  

- Cliquer sur "Calcul lourd (AsyncTask)"  
 La ProgressBar doit progresser de 0 à 100  



##Bonnes pratiques

-  Ne pas exécuter de tâches longues sur le UI Thread  
- Ne pas modifier l’UI depuis un thread de fond  
-  Utiliser Handler ou AsyncTask pour mettre à jour l’UI  



## Résultat

- Interface fluide  
- Pas de blocage (ANR)  
- Bonne gestion des threads  
- Mise à jour correcte de l’UI  

