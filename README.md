<img width="1536" height="646" alt="ChatGPT Image 28 janv  2026, 12_18_32" src="https://github.com/user-attachments/assets/2a47c32c-d386-4d59-9961-78c190b74697" />

📊 EventCollecte — Event de collecte pour Minecraft (Skript)

📦 Informations générales
Nom : EventCollecte
Auteur : Benjinski
Version : 1.0
Type : Skript serveur
Dépendances : Skript, skript-yaml
Langue : Français
Fichier principal : event_collecte.sk

📝 Description  
EventCollecte est un système d’event de collecte dynamique pour Minecraft.  
Les joueurs donnent des ressources via un **menu GUI interactif**, gagnent des **points persistants**, et s’affrontent dans un **classement Top Event**.

L’event fonctionne avec une **rotation automatique des items**, un **stockage YAML persistant**, et expose des **variables API** réutilisables dans d’autres Skripts (scoreboard, hologrammes, GUI, tablist, etc.).

Toutes les données sont stockées localement côté serveur, sans base de données externe.

⚙️ Fonctionnalités  
🔄 Rotation automatique de 3 items uniques  
🎒 Menu GUI interactif (`/event`)  
🧮 Système de points persistants (YAML)  
🏆 Classement Top 10 stable  
⏱️ Anti-spam clic intégré  
👑 Commandes administrateur complètes  
🔌 Variables API réutilisables  
🚀 Optimisé, compatible reload et restart serveur  

📂 Installation  
1. Placez le fichier :
  event_collecte.sk dans : /plugins/Skript/scripts/

2. Redémarrez le serveur ou exécutez :
  /sk reload event_collecte


💬 Commandes disponibles  

👤 Joueurs  
/event  
→ Ouvre le menu de l’event  

/event top  
→ Affiche le classement Top Event  

/event points  
→ Affiche vos points personnels  

👑 Administration (permission : event.admin)  
/event force  
→ Force la rotation des items  

/event setpoints <joueur> <montant>  
→ Définit les points d’un joueur  

/event addpoints <joueur> <montant>  
→ Ajoute des points à un joueur  

/event resetpoints <joueur>  
→ Réinitialise les points  

/event remove <joueur>  
→ Supprime un joueur de l’event  

🧱 Ajout des items de collecte  
Les items de l’event sont définis dans la **pool** :

```skript
add "diamond|5|&bDiamant|true|&7Rapporte &a5 &7points par diamant" to {event::pool::*}
```

Format :
material | pointsParItem | nomAffiché | glow(true/false) | lore
Exemples :
```skript
add "netherite ingot|20|&8Lingot de Netherite|true|&7Rapporte &a20 &7points" to {event::pool::*}
add "blaze rod|4|&6Bâton de Blaze|false|&7Rapporte &a4 &7points" to {event::pool::*}
```

Les 3 items actifs sont choisis automatiquement à chaque rotation.

🗃️ Stockage des données
Les données sont enregistrées dans : plugins/Skript/data/event_points.yml
Structure :
```skript
players:
  UUID:
    name: Pseudo
    points: 150
```
📌 Variables API réutilisables

Points d’un joueur : {event::points::%uuid of player%}
Top Event sur une seule ligne : {event::topText}

📌 Notes
Les données sont sauvegardées automatiquement
Compatible avec tous les modes de jeu
Fonctionne uniquement côté serveur
Aucune base de données externe requise

📜 Licence
Skript libre d’utilisation et de modification pour un usage personnel ou communautaire.
Merci de conserver les crédits de l’auteur.
