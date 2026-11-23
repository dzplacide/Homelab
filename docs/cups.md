# Serveur d'impression CUPS — en cours

[← Retour au homelab](../README.md)

| Élément | Valeur |
| --- | --- |
| Imprimante | Canon imageCLASS MF264dw, port Ethernet |
| Adresse de l'imprimante | 192.168.20.30 (VLAN 20, via le TL-SG105) |
| Serveur CUPS | `client-VM`, Ubuntu (192.168.10.21, VLAN 10) |
| Clients | Postes Windows 11 du domaine `samba.lan` |

## Objectif

Centraliser l'impression : les postes du domaine impriment par le serveur CUPS, qui envoie les travaux à l'imprimante réseau dans un autre VLAN. Cela met aussi en pratique le routage inter-VLAN.

## Étapes

- [x] Imprimante branchée en Ethernet dans le VLAN 20 avec une adresse fixe
- [ ] Installation de CUPS sur `client-VM` et ajout de l'imprimante
- [ ] Partage de l'imprimante et test d'impression depuis Windows 11
- [ ] Documentation des commandes et captures d'écran

*Après les tests, l'imprimante retourne en Wi-Fi pour le reste de la maison.*
