# A propos des données

Les fichiers utilisés pour créer le réseau OSOS sont les suivants:

- `userscomplete_dehydrated.jsonl` comprenant la liste des ID de tweets des 80 utilisateurs identifiés à partir des listes des participants publiées sur les sites Web des conférences CHAOSScon et FOSDEM et des "feeds" Twitter publics des comptes officiels des conférences @CHOASSproj et @FosdemResearch

    - ces données ont été "déshydratées" pour être conformes aux [conditions d'utilisation de Twitter](https://developer.twitter.com/en/developer-terms/policy#6._Be_a_Good_Partner_to_Twitter). Afin de reproduire les résultats, il est possible de les "réhydrater" en passant l'API de Twitter à l'aide de Twarc qui prévoit une commande à cet effet: `twarc dehydrate tweets.jsonl > tweet-ids.txt `

- 80 fichiers de type `follower_ids{}.txt` comprenant la liste des "user ID" des abonnés pour chaque utilisateur

- 80 fichiers de type `friend_ids{}.txt` comprenant la liste des "user ID" des abonnements pour chaque utilisateur

## Collecte:

- Les données ont été collectées via l'API de Twitter avec [Twarc](https://github.com/DocNow/twarc)

## Commandes:

- Commande qui retourne les métadonnées pour chaque nom d'utilisateur (sreen name):

> twarc users deray,Nettaaaaaaaa > users.jsonl

Fonctionne aussi avec les "user ids":

> twarc users 1232134,1413213 > users.jsonl

Il est possible de l'utiliser avec une liste de "user ids" en format .txt:

> twarc users ids.txt > users.jsonl

## Abonnés et abonnements (*followers* et *friends*)

- Commande qui retourne la liste des "user ids" des abonnés ou des abonnements d'un utilisateur:

> twarc followers deray > follower_ids.txt
> twarc friends deray > friend_ids.txt
