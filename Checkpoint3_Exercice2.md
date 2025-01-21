# Exercice 2 : Manipulations pratiques sur VM Linux

## Partie 1 : Gestion des utilisateurs

#### Q.2.1.1

![Capture d'écran 2025-01-17 105149](https://github.com/user-attachments/assets/8df02787-aa81-402d-89ac-28315f5a8973)

#### Q.2.1.2

Pour mon compte à usage personnel, je lui donnerais le moindre privilège pour qu'il ait accès juste a ce dont il a besoin. Je mettrais également un mot de passe robuste.

## Partie 2 : Configuration de SSH

#### Q.2.2.1

![Capture d'écran 2025-01-17 105551](https://github.com/user-attachments/assets/12079626-d83e-44c9-b7a0-242a2d8c9a68)

#### Q.2.2.2

![Capture d'écran 2025-01-17 110132](https://github.com/user-attachments/assets/6d46129b-28a9-4223-bbda-30161b29d593)

#### Q.2.2.3

![Capture d'écran 2025-01-17 121402](https://github.com/user-attachments/assets/e4d77e27-3d04-48f4-8826-1fa7fcc7a000)
![Capture d'écran 2025-01-17 121634](https://github.com/user-attachments/assets/353e7b9e-5ede-4d3a-acae-ff780e47a85d)


## Partie 3 : Analyse du stockage

#### Q.2.3.1

![Capture d'écran 2025-01-17 110519](https://github.com/user-attachments/assets/70f3e327-583d-49da-bdcd-916c8ef2b729)

#### Q.2.3.2

![Capture d'écran 2025-01-17 110708](https://github.com/user-attachments/assets/55a74779-3ebe-49e4-8cef-ad875c57aff9)

#### Q.2.3.3

![Capture d'écran 2025-01-21 171033](https://github.com/user-attachments/assets/6c1e216a-5cfa-4e62-afac-c1ff6c1668be)


#### Q.2.3.4

![Capture d'écran 2025-01-17 124619](https://github.com/user-attachments/assets/d3b4446a-50e9-43d0-a62e-41fc225c4f71)
![Capture d'écran 2025-01-17 124704](https://github.com/user-attachments/assets/57d6f225-27c3-4337-9158-c534ea53f244)

#### Q.2.3.5

![Capture d'écran 2025-01-17 113258](https://github.com/user-attachments/assets/42ad7c60-2df2-4054-9b99-8c7aacc747f3)

## Partie 4 : Sauvegardes

#### Q.2.4.1

Bareos-dir (Director): Composant central qui gère la configuration, la planification des travaux de
sauvegarde
Bareos-sd (Storage Daemon): Responsable du stockage physique des données de sauvegarde sur
les supports de stockage qu'il reçoit des clients.
Bareos-fd (File Daemon): C'est l'agent installé sur chaque client qui permet à Bareos-dir de gérer les
sauvegardes.

## Partie 5 : Filtrage et analyse réseau

#### Q.2.5.1

![Capture d'écran 2025-01-21 172151](https://github.com/user-attachments/assets/d8c2df63-71ce-4d82-8c9b-57a163932ef1)

#### Q.2.5.2

ct state established, related accept : les retours de connexions déjà établies.

iifname "lo" accept autorise le trafic local.

TCP dport 22 accept autorise les connexions TCP destinées au port 22 (port SSH).

IP protocol icmp accept autorise les pings IPV4.

IP6 nexthdr icmpv6 accept autorise les pings IPV6.


#### Q.2.5.3

ct state invalid drop : les paquets ne pouvant pas être identifiés à une requêtes.
Et tout le reste qui n'est pas en accept.

#### Q.2.5.4

nft add rule inet inet_filter_table in_chain tcp dport { 9101-9103 } ct state new accept

## Partie 6 : Analyse de logs

#### Q.2.6.1

journalctl -u ssh | grep 'Failed password' | tail
