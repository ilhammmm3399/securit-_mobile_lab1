# LAB 1 : Mise en place du lab (Mobexler + snapshot clean)

## Étape 1 — Télécharger Mobexler (OVA) et tracer le téléchargement
Après le telechargement de l'OVA depuis le lien officiel, on verifie l'integrite:
![WhatsApp Image 2026-02-06 at 17 54 43](https://github.com/user-attachments/assets/9cc6803d-438f-4451-bc63-50ecee1e3791)



*le hash local correspond bien au SHA256.*

## Étape 2 — Importer l’OVA dans VMware

1. Configuration Réseau (VMware):

Nous avons mis en place deux interfaces réseaux distinctes ;
* **NAT (VMnet8) :** Pour l'accès à internet (téléchargement des paquets).
* **Host-Only (VMnet1) :** Pour la communication privée avec l'hôte (ADB) sans exposition externe.
![WhatsApp Image 2026-02-06 at 18 03 31](https://github.com/user-attachments/assets/ab9d74eb-011c-4ea3-8bc0-1c9aba190b87)

## Étape 3 — Premier démarrage + connexion
*Connexion et accès au bureau.*
![WhatsApp Image 2026-02-06 at 17 47 18](https://github.com/user-attachments/assets/e7cda056-2750-488e-8711-1e6e78a1768e)

## Étape 4 — Vérifier le réseau (tests “santé”)

1) Vérifier IPs:

*L'interface `ens33` était UP mais sans IP, comme solution j'ai utiisé `dhclient`* 

![WhatsApp Image 2026-02-06 at 17 26 38](https://github.com/user-attachments/assets/4546bb9a-5b77-4885-a2c1-db39629ab9d6)





3) Vérifier route par défaut et test d'Internet (ping IP + ping DNS)

![WhatsApp Image 2026-02-06 at 17 28 28](https://github.com/user-attachments/assets/7ae44645-d8fd-44cd-a3f9-7b1333416b68)




## Étape 5 — Créer le snapshot “CLEAN” (baseline)

1) Créer le snapshot après la réussite des étapes précédent (OS installé, Réseau OK, Outils de base installés).
VM → Snapshot → Take Snapshot
2) Test de Restauration:
1.  Création d'un fichier test.
![WhatsApp Image 2026-02-06 at 17 47 23](https://github.com/user-attachments/assets/e4022909-f904-4f65-83e6-03549cceec65)

2.  Restauration du snapshot `CLEAN_BASELINE_TP1`:

![WhatsApp Image 2026-02-06 at 17 47 28](https://github.com/user-attachments/assets/7bb669d8-3840-4d3a-b204-8b40bf9c15e4)

4.  Vérification :
5.  Le fichier test a bien disparu, le système est revenu à son état initial.

![WhatsApp Image 2026-02-06 at 17 47 18](https://github.com/user-attachments/assets/45c1c103-c05c-4ae4-9421-2e7e0b2bbc9d)


## Étape 6 — Préparer la cible Android

1. Developer Options + USB debugging activé.
2. Peripherique USB connecté à la VM
3. Vérifier ADB dans Mobexler
![WhatsApp Image 2026-02-06 at 17 41 18](https://github.com/user-attachments/assets/16c6d1ab-5738-40d7-ba3d-f45a17a0332f)
